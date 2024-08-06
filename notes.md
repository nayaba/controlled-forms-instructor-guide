DRAW MVC

Once upon a time there was a view.  He was really happy painting the DOM.  Sometimes the Model would give some nice data to paint.  He knew really well how to paint the UI given all the data.  The data was a username, the points and a color.  

But then the model gave a new username and he had to learn how to update his painting.  To do that he had to keep track of a username div - he dutifully updated the DOM directly.

Then the model provided an update to the points.  Once again he must keep track of a DOM node - this time the points div.  He dutifully updated the DOM in place.

Then the model updatd the color, and once again the view added a new DOM node to his list of nodes to track.  He then updated the color, right there on the DOM.

The model _kept_ giving updates and the view had a hard time keeping track of all the nodes, especially when the order of the updates mattered.



Inputs in react are controlled so there is one soure of truth.  To make a form a controlled input we need to tie it to state.

# Controlled vs. Uncontrolled Components

## Uncontrolled Components

Components that keep track of their own states and release data only when some event occurs (that is the submit event for HTML forms)

## Controlled Components

Components that do _not_ keep track of their own state - all state is passed in as props (in the case of forms, that's when we use the useState Hook with text inputs - useState's state acts as a prop)



Controlled forms allow us to do validation _while_ the user is typing and before they've hit submit, the user can get feedback.