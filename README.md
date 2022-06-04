# modalWindow

Modal Window project using HTML, CSS and Javascript.

This project taught me how to work with classes when working with an onClick addEventListener.

The addEventListener() method is the recommended way to register an event listener. The benefits are as follows:

It allows adding more than one handler for an event. This is particularly useful for libraries, JavaScript modules, or any other kind of code that needs to work well with other libraries or extensions.
It works by adding a function, or an object that implements EventListener, to the list of event listeners for the specified event type on the EventTarget on which it's called. 

For example, working with classes in opening a modal with a class of 'hidden' looks like this:

modal.addEventListener('click', function () { 
      console.log('Button clicked');
      modal.classList.remove('hidden');
    })
  );
  
 // Selects all Classes
 const btnsOpenModal = document.querySelectorAll('.show-modal');
 
 Important lesson learned here is that to refactor and make your code more readable, use functions to minimize repitition.  in this example we created a function to close the modal and simply entered the function name to an event listener: 
 
 const closeModal = function() {
    modal.classList.add('hidden');
    overlay.classList.add('hidden');
}
 
btnCloseModal.addEventListener('click', closeModal);
overlay.addEventListener('click', closeModal)

For utilizing keypress events, we use the 'keydown' handler which in turn makes every button on your keyboard part of an object.  To access the escape button we add the event listener and create a function that takes in the event as its parameter:

document.addEventListener('keydown', function (e) {

  if (e.key === 'Escape' && !modal.classList.contains('hidden')) {
    closeModal();
  }
});

To be continued...
