JavaScript coding guidelines collection
==================

Here are some of the guideline that would help us keep our JS code well organized, readable and maintainable. Most of these guidelines are based on external sources and some we have derived based on number of project executions that we have done. We have also included guidelines for AngularJS code.

## <a name='TOC'>Table of Contents</a>
  1. [JS General](#js-general)
  2. [AngularJS](#angularjs)

## JS General
**airbnb** has release a comprehensive JS guidelines [available here](https://github.com/airbnb/javascript). This would be the first resource to go to.

- Use conditional operator `:?` if you only plan to set one value.
```javascript
//bad
if(condition) { 
   data = value1;
}
else {
   data = value2;
}

//good
data = condition ? value1 : value2;
```

##AngularJS 
- [**Understanding Scopes**](https://github.com/angular/angular.js/wiki/Understanding-Scopes): Read and understand this before thinking of any serious AngularJS development.
- **Read AngularJS Guide**:[This guide](https://github.com/johnpapa/angularjs-styleguide) by John has some good pointers for AngularJS development 
- **Use Model Classes**: JS allows us to use any object without defining classes (constructor function) still it is better to explicity declare model classes. This helps in clearly communicating the intent of the model and what the view as coded against.
- **Shared Model**: Use AngularJS service to share Model across, modules. Do not duplicate models. The idea is derived from [this post](https://medium.com/opinionated-angularjs/2e6a067c73bc).
- **Group Shared Model**: For large implementation service per model becomes unwieldy, as DI count increase. Group models based on feature\functionality and put them in a single service

```javascript
// declare
myModule.factory("UserModel", [function () {
    function User(args) { }   
    function Address(args) { }
    function Education(args) { }
    return {
        User: User, Address: Address, Education: Education
    };
}]);

//use
$scope.user=new UserModel.User();
```
### App Structure
- **Folder + Module per feature**: Create a folder for each feature and a corresponding module too. The folder will contains controllers and services and maybe filters and directive. 
Remember directives and filters are mostly shared components and hence should go into `shared` folder. Look at [this post](http://cliffmeyers.com/blog/2013/4/21/code-organization-angularjs-javascript) too for other organization techniques.
This module separation may help us in lazy loading in future. Register all the modules defined in folders in `app.js` in the root folder.
