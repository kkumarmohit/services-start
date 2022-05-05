# MyFirstApp

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 6.0.0.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

## Service
A service can help to share some common data, implement some common functionality across classes.
To inject a service based on DI pattern, we simply need to provide the service type in "provider" attribute of a component which intends to use that service and
add a property in the construtor of the component to hold the instance of the service.
A service can also help in communicating between components

## Hierarichical Injector
In angular there are broadly three levels of injection of services:
1: AppModule: Same instance of service is available appication wide
2: AppComponent: Same instance of service is available for app component and all its child component (but not for other services)
3: Single component (with no child component): A separate instance will be provide to the specific component.

The instances always propogates downward in angular.

## Injecting services into a service
In older version of angular, @Injectable decorator is used on the service which will itself expect an another service to be injected. No need of decorator on child service
In newer version of angular, @Injectable can be used on either parent or child service.

## Note

Instead of adding a service class to the providers[]  array in AppModule , you can set the following config in @Injectable() :

@Injectable({providedIn: 'root'})
export class MyService { ... }

This is exactly the same as:

export class MyService { ... }
and

import { MyService } from './path/to/my.service';
 
@NgModule({
    ...
    providers: [MyService]
})
export class AppModule { ... }

This has an advantage of lazy loading.