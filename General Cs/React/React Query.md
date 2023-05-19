#tags
Date: {{5/18/2023}}

Send data to server and retrieve data from a server. This is a context that can be accessed anywhere so you hvae to use the provider.

**External Links:**
[Video Going Over It](https://www.youtube.com/watch?v=-bEzt5ISACA)

## queryClient
This is the main object, it for one retrieves data and secondly caches the data for EFFIENCY (Noice). You do thise by calling fetch(Method) on it, it will then check you're query if it's cached return, otherwise it will go cache and etc. 

**Example**
```javascript
const queryClient = new QueryClient();

return (
	<QueryClientProvider>
	</QueryClientProvider>
);
```


## useQuery
useQuery allows you to create data handlers that work with promises, so you no longer need a useEffect to call it or anything, you can just use useQuery and the value you get can be returned

**Example**

```javascript

const (data: idk ) = useQuery(["queryidentifier"], () => fetch(), {initialData: []})
```