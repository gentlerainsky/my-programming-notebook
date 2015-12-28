#Javascript Note

###Annonymous Function Invocation !function() {} ()
**Usage**: To invoke annoymous function. Normally you can't just type function() to invoke it because the interpreter will think that it is function declaration. Putting ! (exclamation mark: NOT operator) in front of the function will make it know that it need to evaluate to find it value.
**How to use**: Add an ! in front of the annonymous function. 

```javascript
!function()
{
    //function body
}()
```