# {{React Native}}
#tags
Date: {{5/18/2023}}

A Doc Covering Everyhting you need for React Native State Mangement

**External Links:**
* [Youtube Video](https://www.youtube.com/watch?v=-bEzt5ISACA)

**Methods**
* Use State

## Use State
Use state is essentially used as a variable holder for variables that should be rerendered on screen when they change as the assignment of these variables initiates a rerender .
**Important**

If the value of the intiial variable an't be inferred you have to create an interface and use the generic syntax to tell the language what the type it (TypeScript Rocks BABY)
**Example**

## Use Reducer

### Reducer Pattern
The reducer  pattern is a pattern which takes the current value and the value at the current index, it should reutrn the next current value

**Example**
```javascript
const numbers = [10,20,30];

numbers.reduce((cv, n) => {return cv + n;}, 0);
```
### Reducer
* Returns the current state
* Returns a dispatch (way to invoke reducer function)
* useReducer((state, action))

**Action Paramater**
* It's just a json object but convention
* action.type = type of call (as reducer can be multiple types of calls)
* action.payload = data for the call 
* Reducer pattern is helpful as it replaces setValue() in useState with somethig more dynamic and complex

## Use Memo
useMemo is used for when a complex operaiton needs to run but you don't want to rerun it every render, only when the dpendenies change.

**When To Use**
* Complex Operations

**Dependency Array**
* Contain everything that is read


## Use Callback
* Essentially UseMemo but for callbacks

Use callback instead of calling the function returns the function itself, so when making annonomous function you pass around, you can use useCallback to stabalize the refrence between renders


## Use Effect

useEffect is used for when you want to run a function only when variables change. Usually you give this nothing and ues it to run functions once so that you don't create an infinite loop. Use effect is used to run side operations, data isn't cahched like useMemo but rather the function just runs whenever the dependacy array changes, with an inital run in the beginning.

**Key Details**
* Use effect Runs ***After*** The render and every subequent update

**Fallbacks**

* If you are responding to user input you should use callbacks and not use memo
* Make sure useMemo does ***not*** depend on a value that it uses


## Use Ref

**Usage**

```javascript
const myRef = useRef(null);

useEffect(() => {
	myRef.current;
}, []);
```

**Important**
* The value in useRef must be accessed by the ***.current*** method




## Custom Hooks
A hook is anything like useState and useMemo, you can create you're own. The ones you create are usually mixtures of different default hooks.

You define these as normal fucniton
* When creating 

## Context
Context enables you to use data without passing it down the tree as a prompt as many times as needed until it gets to the point that you want it to be at.

**How**
In order to pass down the context, components that will use the context must be wrapped by a context provider. 


**Important**
* Example of creating a context
```javascript
const AppContext = createContext("yeetboi");
```
* The context you create instiatntes a context provider
```javascript
return (
	<AppContext.Provider value="dark">
		<Text>Hello</Text>
	</AppContext.Provider>
);
```
* The context should be in a different file and globally accessible as it needs to be refrnees for places lower down the DOM to access it
**Usage**
Once you've create you context and wrapped the interals with the context, you can use it with ***useContext(context)***
```javascript
const theme = useContext(AppContext);
```

* Accessing the data within useContext should have an assocaiated hook rather then directly accessing it with useContext. the contention is use_Source    
* Seperate the data into another file, thise file should have
	* AppContext
	* AppProvider - exported
	* useAppContext() - exported
	
It's also important to understand how these work, so the data you have can be callbacks that change the state. so useAppSource which is the function that returns the data for AppContext should retunr the vales that can be used and methods that cna edit them. It should then use the builtin methods for state management in order to make sure that the value changes when you want to change it. 

