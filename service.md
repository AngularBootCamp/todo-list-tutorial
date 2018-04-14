# Service

## What and why

In Angular, a service is (typically) a JavaScript class that's responsible for performing a specific task needed by your application. In our todo-list application, we'll use a service to save all the tasks, and use it by injecting it into the components.

## Create

In order to create a new service with the Angular CLI, make sure you're in the root folder of your application, then enter this command:

```
ng g s todoList
```

This command will generate the service and put it under `src/app/todo-list.service.ts`.

## Provide in ngModule

To start using the service, we first need to provide it in an NgModule. Start by adding this code in `/src/app/app.module.ts`:

```javascript
import { TodoListService } from './todo-list.service';
```

Next, add the service to the `providers` array, so that the NgModule looks like this:

```javascript
@NgModule({
  declarations: [
    AppComponent,
    InputComponent,
    ItemComponent,
    ListManagerComponent
  ],
  imports: [
    BrowserModule
  ],
  providers: [TodoListService],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

This tells Angular to provide (that is, create and inject) an instance of our service when we ask for it anywhere in our application.

## Move list from component to service

We now need to move the `todoList` array from the component to our new service. The service will now have:

```javascript
  private todoList = [
    { title: 'install NodeJS' },
    { title: 'install Angular CLI' },
    { title: 'create new app' },
    { title: 'serve app' },
    { title: 'develop app' },
    { title: 'deploy app' },
  ];
```

## Create method on service to return the list

Now go to the generated service file, `src/app/todo-list.service.ts`, and add a `getTodoList` method that will return the `todoList` array. The service will look like this:

```javascript
import { Injectable } from '@angular/core';

@Injectable()
export class TodoListService {

  private todoList = [
    { title: 'install NodeJS' },
    { title: 'install Angular CLI' },
    { title: 'create new app' },
    { title: 'serve app' },
    { title: 'develop app' },
    { title: 'deploy app' },
  ];

  constructor() {
  }

  getTodoList() {
    return this.todoList;
  }
}
```

## Inject into list-manager component and use the service

After creating the service, we can inject it into our list-manager component. Go to `src/app/list-manager/list-manager.component.ts` and add the following import code:

```javascript
import { TodoListService } from '../todo-list.service';
```

Now remove the `todoList` array, but keep the `todoList` member:

```javascript
  todoList;
```

Change the constructor to be:

```javascript
constructor(private todoListService:TodoListService) { }
```

And now use the service to assign the `todoList` array inside the `ngOnInit` method:

```javascript
ngOnInit() {
  this.todoList = this.todoListService.getTodoList();
}
```

