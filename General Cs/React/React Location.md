
#tags
Date: {{5/18/2023}}

This is primarily used for web solutions and not apps, so if I decide to create a website this would most likely be the best way to design the website 

React Location enables you to maginiate and move through pages and create different pages. It essentially allows you to create a multipage application.

**External Links:**
[Video](https://www.youtube.com/watch?v=-bEzt5ISACA)

## Main Application
You saround your main app with Router and feed it in routes and location. You import Outlet and use that so that whatever the content in the orute is, it essentially replaces Outlet.

**Example**
```javascript
return (
	<Router location={location} routes={routes}>
		<Outlet />
	<Router>
);
```



## Routes

You create a routes object which is an array that holds the different routes that you ca go in, these routes are then links to Functions that render so that when you switch, it will render these on screen

## Switching Routes

Saround the things that are clicked that send you to another route withn ***Link***

**Example**

```javascript
return (
	<Link key={dataForPath} to={`/path/${dataForPath}`}>
		<Text> HHE</Text>
	</Link>
);
```

## useMatch

useMatch is used to get the id of whatever called this speicifc route, so the ui elments within the routes list would use useMethod inside their funcitons to access them. (The id would be whatever you put inside youre route ***/human/:id***)

**Example**

```javascript
const {
	params: {id},
} = useMatch();
```
