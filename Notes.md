## What are Forms/Introduction

Need to handle Forms through Angular, instead of submitting to a server. Check if a form is valid, change how form is displayed, put red borders with inactive forms and such.

So how does Angular handle forms?

## Why do we need Angular's help?

EXAMPLE FORM

    <form>
    <label>Name</label>
    <input type="text" name="name">
    <label>Mail</label>
    <input type="text" name="email">
    <button type="submit">Save</button>
    </form>

![Forms](image.png)

Would be helpful if some metadata was stored if valid, and not stored if it's not valid.

Gives JS form of your form to see state of form and work with it?

## Template-Driven (TD) vs Reactive Approach

![Alt text](image-1.png)

## An Example Form

## TD: Creating the Form and Registering the Controls

Ah! We once again see ngModel, as we did with 2-way data binding. But with 2-way, [{ngModel}] was like this. Now we will revisit this, but for now, it's without wrapping.

Enough to tell A, hey this is actually a control of my form!

*select* is much like *input*

## TD: Submitting and Using the Form

We get an NgForm object, we didn't create, and can see the prop in the console. If we expand the key value pairs we see the names of the controls in our attributes!

## TD: Understanding Form State

Dirty is true b/c we changed something about the form? If we don't type the input, we don't get... dirty

## TD: Accessing the Form with @ViewChild

So we don't need to use (f), we can use @ViewChild in the AppComponent.ts

## TD: Adding Validation to check User Input

SO now we're going to do validators!

Here, required is acting as a stand in director/validator? In the HTML. Will be treated as invalid if empty...

*A list of all available built-in Validators can be found in a later video...*

And now the form tracks it, queries it, to see if it's submitted or not!

## Built-In Validators & Using HTML5 Validation

Which Validators do ship with Angular?

Check out the Validators class: https://angular.io/api/forms/Validators - these are all built-in validators, though that are the methods which actually get executed (and which you later can add when using the reactive approach).

For the template-driven approach, you need the directives. You can find out their names, by searching for "validator" in the official docs: https://angular.io/api?type=directive - everything marked with "D" is a directive and can be added to your template.

Additionally, you might also want to enable HTML5 validation (by default, Angular disables it). You can do so by adding the ngNativeValidate to a control in your template.

## TD: Using the Form State

Now we are trying to make the form invalid and red at the sections that are NOT filled out!

## TD: Outputting Validation Error Messages

How can we put an error message?

## TD: Set Default Values with ngModel Property Binding

Setting a default question in the dropdown!

## TD: Using ngModel with Two-Way-Binding

We can see the answer we type out!

## TD: Grouping Form Controls

What if we want to group username and email, input and secret answer?

*if there's an error, it's HERE

## TD: Handling Radio Buttons

Erasure of data, often leads to the erasure/dismissal of people

<https://medium.com/omidyar-network/erasure-b8fc85eae619#:~:text=Erasure%20refers%20to%20the,recorded%20history%3B%20and%20how%20their>

## TD: Setting and Patching Form Values

patch value= override parts of the form,
set value= set specific data at the start

## TD: Using Form Data

Submit the form and got the data we wanted to extract!

## TD: Resetting Forms

Now when we submit our form, it resets itself

## Assignment: Template-driven Forms

So now we are going to code a new form! One with the following Inputs and Validators:

1. Mail address (should not be empty and should be an email address)
2. A dropdown which allows the user to select from three different subscriptions ("basic", "advanced", "pro"). Set "Advanced" as default
3. A password field (should not be empty)
4. A submit button

Display a warning message if the Form is invalid AND was touched. Display a warning message below each input if it's invalid.

Upon submitting the form, you should simply print the Value of the Form to the Console. Optionally, display it in your template.
==============