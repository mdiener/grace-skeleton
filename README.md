Grace Skeleton
==============

This repository holds the default skeleton for the *Grace* project.


JavaScript Setup
----------------

It is important that you follow the JavaScript setup, or you will not be able to use **Grace**. You can either write all your code in the provided application.js file, or use the structure to split it up. It is highly recommended to split your JavaScript code into single classes, giving each class its own file. This way you will have a much better overview. To do this, **Grace** parses your application.js file and sees if the first line as a *//= require MyClass* in it. This is the starting point, meaning that your first class file should be something like a *main* in other languages. In every JavaScript file you create, you can add the *//= require Path/To/Class/File* at the beginning, to include another file. It is important that you do not add the .js at the end. The following is an example set up:

application.js
```javascript
//= require MyMain

jQuery(document).ready(function() {
    main = new MyProject.MyMain()
});
```

MyMain.js
```javascript
//= require utils/MyUtils.js

Class('MyProject.MyMain', {
    has: {
        log: {
            is: 'r',
            init: MyProject.utils.MyUtils.logWithType
        }
    }

    after: {
        initialize: function() {
            var self = this;

            self.draw('circle'))
        }
    }
});
```

utils/MyUtils.js
```javascript
Class('MyProject.utils.MyUtils', {
    my: {
        methods: {
            logWithType: function(val) {
                console.log(jQuery.type(val), val);
            }
        }
    }
});
```

The folder structure for this would look as following:
<pre>
MyProject
|-- project.cfg
|-- manage.py
`-- src
    |-- index.html
    |-- javascript
    |   |-- MyMain.js
    |   `-- utils
    |       `-- MyUtils.js
    `-- lib
        |-- jquery
        |   `-- jquery.min.js
        `-- joose
            `-- joose.min.js
</pre>

For more information on Joose and the class system go to http://joose.it/.
