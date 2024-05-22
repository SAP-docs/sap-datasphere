<!-- loio685b1e0785ba430ba3d64702cd4dc1b0 -->

# Validating Objects

Objects must be complete and consistent before you can deploy them. Object validation happens automatically as you edit, and any errors and warnings are displayed on the *Validation Messages* button in the top-right corner of the editor.

Each type of object has its own set of validations and each validation has a severity level:

-   *Info* - The message is purely informational and there is no problem with the object.
-   *Warning* - There is an issue with the object, which you should be aware of, but you can still save and deploy it.

    > ### Note:  
    > If you make changes to an object that will impact another object that consumes your object, you will generate warnings.

-   *Error* - There is a serious issue with the object, which will prevent it from running correctly. You can save the object, but you cannot deploy it.

