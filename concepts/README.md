# ![Controlled Forms in React - Concepts](./assets/hero.png)

**Learning objective:** By the end of this lesson, students will be able to explain the concept of React's virtual DOM and its importance in regards to controlled forms in React applications.

## React's virtual DOM


1. **Understanding the DOM:**
   - The DOM (Document Object Model) is the browser's way of representing a webpage as a structured map, with each HTML element as a node.

   > Draw a box on the left labeled "Real DOM."
   > Inside the box, sketch a simplified tree structure with elements like `<div>`, `<h1>`, `<p>`, representing the structure of a webpage.

2. **Virtual DOM Basics:**
   - React uses a virtual DOM, a lightweight, in-memory representation of the real DOM. It acts as a mirror, keeping track of changes without directly affecting the actual DOM.

   > Draw a box on the right labeled "Virtual DOM" and replicate the first tree

3. **Benefits of the Virtual DOM:**
   - **Simplified State Management:** React handles state changes efficiently, ensuring the UI reflects the current state without manual intervention.
   - **Consistency:** It maintains synchronization between application state and visual output, reducing errors and simplifying development.

   > Draw a circle or box above the virtual DOM labeled "Component State/Props." --> Source of Truth

4. **Reconciliation Process:**
   - React will compare the new virtual DOM (resulting from the updated state) with the previous virtual DOM; called reconciliation
   - **When Reconciliation Occurs**
        1. **State Updates:** triggers a re-render for that component. 
        2. **Prop Changes:** can cause a re-render

    > Between the virtual and real DOM, draw a box labeled "Diffing Algorithm."

 ### Flow

1. **Initial Render**
   - "Component State/Props" ---> "Virtual DOM" `Render with State/Props`
   - "Virtual DOM" --> "Real DOM" `Initial Render`

2. **State/Prop Change**
   - "Component State/Props" ---> "Virtual DOM" `State/Prop Change`
   - **Change the virutal DOM somehow**

3. **Reconciliation Process**
   - `Apply Updates` "Real DOM" <--- "Diffing Algorithm" ---> "Virtual DOM" `Calculate Changes`


---

## Controlled Inputs and Forms in React

   - Controlled inputs allow React components to manage form states directly, keeping input values synchronized with component state.

   - An event handler updates the state with every keystroke, keeping the input field in sync with state changes.

   - The big advantage with forms is that you can validate with every keystroke (not _after_ the form has already been submitted)

### Visual Aid: Whiteboard Diagram

**Title: Controlled Forms in React**

Draw a flowchart to illustrate the relationship between state, input elements, and handler functions.

1. **State Variable** 
   - Draw a box labeled "State Variable" (e.g., `cityInput`) ---> "Input Element" `Value`
   
2. **Input Element**
   - Draw a box labeled "Input Element" ---> "Handler Function" `onChange`

3. **Handler Function**
   - Draw a box labeled "Handler Function" (e.g., `handleChange`) ---> "State Variable" `Updates State`

**Ask students**:  
> **What role does state play in a controlled input?**
>
> State serves as the single source of truth for the input's value. It allows React to manage the input's value and ensures that any changes to the input are immediately reflected in the component's state.

> **How does a handler function affect the input's state?**
>
> A handler function updates the input's state whenever the input's value changes. It captures the new value from the input and updates the state accordingly.