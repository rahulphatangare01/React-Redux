# Redux

      Redux is a state management library often used with React to manage the state of an application in a more predictable and consistent manner

## Core Concepts of Redux

     1. Single Source of Truth

         Redux Stores the entire state of the application in a single javaScript object called the store.
         This centralization makes it easier to manage and debug state changes.


     2. State is Read-Only:
        The state in Redux is immutable. The only way to change the state is by dispatching an action.
        This ensures that all state changes are explicit and trackable.


     3. Changes are Made with Pure Functions:
        To specify how the state tree is transformed by actions, Redux relies on pure functions called reducers.
        Reducers take the current state and an action as arguments and return a new state.

## Key Component of Redux

     1. Store:
        The store holds the application state. It is created using the *`createStore`* function from Redux.

      ```javaScript

        import {createStore} from 'redux';
        const store = createStore(rootReducer);

      ```

     2. Actions:
         Actions are plain JavaScript objects that describe what happened. They must have a type property indicating the action type. Optionally, they can have a payload property containing additional information.

      ```javaScript
        const ADD_TODO = 'ADD_TODO';
        const addTodo = (text) => ({
            type: ADD_TODO,
            payload: { text }
            });
      ```

     3. Reducers:
        Reducers are pure functions that take the current state and an action, and return a new state. They must not mutate the state but instead return a new object.

        ```javaScript

            const initialState = {
            todos: []
            };

            const todoReducer = (state = initialState, action) => {
            switch (action.type) {
            case ADD_TODO:
            return {
            ...state,
            todos: [...state.todos, action.payload.text]
            };
            default:
            return state;
            }
            };

        ```
     4. Dispatching Actions:
         Actions are dispatched to the store using the dispatch method. This is how you trigger a state change.


      ```javaScript
      store.dispatch(addTodo('Learn Redux'));

      ```
     5. Selectors:
     Selectors are functions that extract specific pieces of state. They help in organizing how the state is accessed.

```javaScript

          const getTodos = (state) => state.todos;


```
