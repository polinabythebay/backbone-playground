## Backbone

### Prerequisites

Familiarity with JavaScript, including:

- Closures.
- How the keyword `this` works.
- Prototypical inheritance.
- Psuedoclassical classing.

Comfortable with [Underscore.js](http://underscorejs.org/). Especially its method signatures on collections.

Comfortable with jQuery, Ajax, HTML, CSS. See below for an example.

### Intro

You are a budding web developer. You know how to weild jQuery, Ajax calls, HTML, CSS, and you understand the ins and outs of the major parts of the JavaScript language. What are you missing out on?

Well, the great thing about jQuery is that you can do a lot in a few lines of code. The following code:

- Listens for page events
- Listens for user events
- Listens for network IO
- Parses GET response
- Does HTML templating

```
$(document).ready(function() {
    $('#new-status form').submit(function(e) {
        e.preventDefault();

        $.ajax({
            url: '/status',
            type: 'POST',
            dataType: 'json',
            data: { text: $('#new-status').find('textarea').val() },
            success: function(data) {
                $('#statuses').append('<li>' + data.text + '</li>');
                $('#new-status').find('textarea').val('');
            }
        });
    });
});
```
What are the problems with above code? 

- Well, in its current state it's nearly impossible to test.
- If we followed the single responsibility principle, then it would make it easier to test and reuse. Currently it doesn't do that.
- We want to decouple the DOM and Ajax.

### Goals of Backbone

- Strive towards separation of concerns, single responsibility, and the ability to reason in isolation.


### Resources

- [Backbone, the Primer](https://github.com/jashkenas/backbone/wiki/Backbone,-The-Primer)
- [Step by Step jQuery to Backbone](https://github.com/kjbekkelund/writings/blob/master/published/understanding-backbone.md/)
- [The BackboneJS way of thinking](http://learn.eastros.com/2013/04/20/the-backbonejs-way-of-thinking/)
- [What is a model?](https://cdnjs.com/libraries/backbone.js/tutorials/what-is-a-model/)
- [What is a view?](https://cdnjs.com/libraries/backbone.js/tutorials/what-is-a-view/)
- [What is a collection?](https://cdnjs.com/libraries/backbone.js/tutorials/what-is-a-collection/)
- [How do JS timers work?](http://ejohn.org/blog/how-javascript-timers-work/)
