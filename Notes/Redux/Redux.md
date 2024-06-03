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
