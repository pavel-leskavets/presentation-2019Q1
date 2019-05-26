# presentation-2019Q1
Hello, the topic of my presentation is a "Comparison of state management solutions for React"     
`(Slide - Presentation topic)`  
The component-based approach of React and other frontend frameworks like Vue and Angular has changed the way our web looks like today. One massive part of their success story is the way components communicate and share state with each other. This empowers the developer to create maintainable software by separating different parts of logic and state into dedicated components that pushes our future web.  
`(Slide - The component-based approach)`  
In this presentation I will present multiple state-of-the-art state management libraries  
`(Slide - What will be discussed)`  
In an application, state is the interface between your data from any kind of backend or local change and the representation of this data with UI-elements in the frontend. State is able to keep the data of different components in sync because each state update will rerender all relevant components.   
`(Slide - What is component state)`  
Redux - a predictable state container for JavaScript apps.  
`(Slide - What is Redux)`  
Redux was first released at June, 2015 by Dan Abramov.  
`(Slide - Author of Redux)`  
Installation  
`(Slide - How to install Redux)`  
The whole state of your app is stored in an object tree inside a single store. The only way to change the state tree is to emit an action, an object describing what happened. To specify how the actions transform the state tree, you write pure reducers.     
`(Slide - Basic Example)`  
This is a reducer, it describes how an action transforms the state into the next state. The shape of the state is up to you: it can be a primitive, an array, an object, or even an Immutable.js data structure. The only important part is that you should not mutate the state object, but return a new object if the state changes.  
`(Slide - Code example)`  
Instead of mutating the state directly, you specify the mutations you want to happen with plain objects called actions. Then you write a special function called a reducer to decide how every action transforms the entire application's state. 
`(Slide - Reducers)`  
Actions are payloads of information that send data from your application to your store. They are the only source of information for the store. You send them to the store using. Actions are plain JavaScript objects. Actions must have a type property that indicates the type of action being performed. Types should typically be defined as string constants.  
`(Slide - What is Actions)`  
The data lifecycle in any Redux app follows these 4 steps: You call store.dispatch(action). An action is a plain object describing what happened. You can call store.dispatch(action) from anywhere in your app, including components and XHR callbacks, or even at scheduled intervals.  
`(Slide - The data lifecycle in Redux app)`  
The Redux store calls the reducer function you gave it. The store will pass two arguments to the reducer: the current state tree and the action. !!!!!Note that a reducer is a pure function. It only computes the next state. It should be completely predictable: calling it with the same inputs many times should produce the same outputs. It shouldn't perform any side effects like API calls or router transitions. These should happen before an action is dispatched.  
`(Slide - Redux store)`  
The root reducer may combine the output of multiple reducers into a single state tree. How you structure the root reducer is completely up to you. Redux ships with a combineReducers() helper function, useful for “splitting” the root reducer into separate functions that each manage one branch of the state tree. Here's how combineReducers() works. Let's say you have two reducers, one for a list of todos, and another for the currently selected filter setting:  
`(Slide - The root reducer)`  
The Redux store saves the complete state tree returned by the root reducer. This new tree is now the next state of your app! Every listener registered with store.subscribe(listener) will now be invoked; listeners may call store.getState() to get the current state. Now, the UI can be updated to reflect the new state. If you use bindings like React Redux, this is the point at which component.setState(newState) is called.   
`(Slide - Code example)`  
Apollo Link State 
Peggy Rayzis from Apollo implemented a library for managing local state as well to avoid the necessity for using a state management library from above when managing the state from the GraphQL Server in your app. You do not even need to consume a GraphQL API to use the expressive query language. You can simply query and mutate your local application state. You define the state of your application by creating an ApolloClientwith LocalLink.   
`(Slide - What is Apollo link state)`  
`(Slide - Code example)`  
From this point on you are able read from your local state by writing GraphQL queries where each top level field includes the @client directive. By appending this directive Apollo knows, that you want to fetch from your local state.  
`(Slide - GraphQL queries)`  
If using Apollo with a GraphQL or REST server you can request those sources as well in one single request. When using apollo-link-rest you can wrap an ordinary REST-resource to be queried and mutated by GraphQL queries/mutations. The result of the query can be accessed with the Query-component of Apollo, that accepts a render-method like the Subscriber in Unstated or the Consumer from the Context API.  
`(Slide - Use Apollo)`  
Conclusion  
`(Slide - Conclusion)`
