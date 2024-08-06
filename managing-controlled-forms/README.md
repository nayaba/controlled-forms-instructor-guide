# ![Controlled Forms in React - Managing Controlled Forms](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to create and manage a controlled form in React.

## Now let's implement a more complex form.

✨ Copy App.jsx and rename copy to SimpleForm.jsx

To get started, replace the existing code in `App.jsx` with this simple form:
 

```jsx
// src/App.jsx

// import the useState() hook
import { useState } from 'react';

const App = () => {
  // add placeholder text for the title
  // we'll use the form to update this state by the end of this lesson
  const [title, setTitle] = useState('The full name will appear here.');

  return (
    <>
      <h2>{title}</h2>
      <form>
        <label htmlFor="firstName">First Name: </label>
        <input id="firstName" name="firstName" />
      </form>
    </>
  );
};

export default App;
```

> **What state variables are necessary to manage this form?**
>
> `firstName` and `lastName` state variables.

## Add new state to track the input

 Declare a new state variable called `firstName`.

```jsx
// src/App.jsx

const App = () => {
  const [title, setTitle] = useState('The full name will appear here.');
  // declaring state with an empty string as the initial value
  const [firstName, setFirstName] = useState('');

  return (
    <>
      <h2>{title}</h2>
      <form>
        <label htmlFor="firstName">First Name: </label>
        <input id="firstName" name="firstName" />
      </form>
    </>
  );
};
```

## Connect state to the input field

> **How do we ensure the input value is controlled by state?**
>
> By setting the input's `value` prop to the corresponding state variable.

With state in place, add a `value` prop to the input and set its value to `firstName`:

```jsx
    <>
      <h2>{title}</h2>
      <form>
        <label htmlFor="firstName">First Name: </label>
        <input
          id="firstName"
          value={firstName}
        />
      </form>
    </>
```

> 🚨 Notice this breaks our input momentarily, as the value is now controlled by state instead of what the user types in.

## Update state with a handler function

Next, we will define a function called `handleFirstNameChange()` to help us change the state controlling our input. Add it to the App component.

```jsx
// src/App.jsx

const App = () => {
  const [title, setTitle] = useState('The full name will appear here.');
  const [firstName, setFirstName] = useState('');

  // when invoked, update the firstName state to equal the new value 
  const handleFirstNameChange = (event) => {
    setFirstName(event.target.value);
  };

  return (
    <>
      <h2>{title}</h2>
      <form>
        <label htmlFor="firstName">First Name: </label>
        <input
          id="firstName"
          name="firstName"
          value={firstName}
          onChange={handleFirstNameChange}
        />
      </form>
    </>
  );
};
```

Confirm that your implemented changes work by typing a value into the input field. With your dev tools open to the React Components tab (and highlighting the App component), you should see the value you typed in reflected in the component's state!

## 🎓 You Do

Now that we can track the value of our input field via state, let's repeat that process for a last name. To do this, we will need to:

1. Create state for the last name. Call it `lastName`.
2. Connect this state to a new input field.
3. Create a function to handle the state change for that input field. Call it `handleLastNameChange`.
4. Test it out and make sure that you can track the elements of state for first name and last name.

Test that you can update your state like you did with the first input field. If you can, you are ready to move forward.
