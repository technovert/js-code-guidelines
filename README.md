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
- [This guide](https://github.com/johnpapa/angularjs-styleguide) by John has some good pointers for AngularJS development 
