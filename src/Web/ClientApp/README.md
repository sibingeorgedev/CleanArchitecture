# CleanArchitecture.Web

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 21.1.5.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.io/cli) page.


# Feature — Due Dates & Filtering

## Changes Appiled

### Backend Changes

- Added `DateOnly? DueDate` to the `TodoItem` domain entity
- Added EF Core migration for creating the nullable `DueDate` column in the database
- Updated the `CreateTodoItemCommand` and `UpdateTodoItemDetailCommand` to accept `DueDate`
- Added `DueDate` validation, should be a future date if provided
- Exposed `DueDate` in `TodoItemDto` via AutoMapper

### Frontend Changes
- Due date has been displayed next to each todo item in the title
- Overdue items highlighted in red with "Overdue" label
- All,Active,Completed filter buttons on the todo list
- Due date date picker in the Item Details dialog

### Tests
- `ShouldCreateTodoItemWithDueDate` verifies due date is persisted on create
- `ShouldUpdateTodoItemDueDate` verifies due date is updated correctly