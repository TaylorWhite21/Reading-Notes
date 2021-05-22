# 09 Forms

Forms allow users to input data that can then be used and manipulated by the application.

There are several form controls used to create a form. However, they also start with a `<form>` tag.
```html
<form></form>
```
A complete form will utilize many different types of controls can even include buttons.
```html
<form action="" method="">
 <ul>
  <li>
    <label for="name">Name:</label>
    <input type="text" id="name" name="user_name">
  </li>
  <li>
    <label for="mail">E-mail:</label>
    <input type="email" id="mail" name="user_email">
  </li>
  <li>
    <label for="msg">this is a Message box:</label>
    <textarea id="msg" name="user_message"></textarea>
  </li>
   <li class="button">
  <button type="submit">Send your message</button>
  </li>
 </ul>
</form>
```
A form can use radio buttons, checkboxes, lists, `<input>` fields, `<textarea>`, and `<label>`. `type=""` is a great place to set attributes, or select radio buttons. The Name attribute can allow you to manipulate it with an id. Maxlength and size can assist in creating the size of the form you desire.
