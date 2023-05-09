# dialoger
#tags
Date: 09-04-2022

Dialoger is a library I will be creating for a basic abstraction around dialogs.

**External Links:**

## Example
```go

type AliceHelloScene struct {
	Text string
	
}






reg.Register(  
   dialog.NewChoice("hello, would you like to be my friend, my name is alise", "yes", "no")  
   .Choice(0).Next(  
      dialog.New("You are now my friend")  
	  .SetUserVariable("alice.friend", true)
    )  
)

reg.Register(
	dialog.NewChoice("would you like to buy an apple?", "yes", "no")
	.Choice(0)
	.BarnchBool(
		func(user Dialoger) true {
			return user.GetBool("alice.friend", false)
		},
		dialog.New("that will be 50$"),
		dialog.New("I only sell apples to my friends")
	)
)

dlog := dialog.Tree("would you like to buy some apples", "yes", "no")
dlog.Choice(0).Branch(
	func(dialoger Dialoger, user Reader) int {
		if user.Get("alice.friend", false) {
			user.ShowUI(applestoreorwhatever)
			return
		}
		return 0
	},
	dialog.New("You aren't my friend yet!")
)
dlog.Choice(1)
	.Next("That's to bad :(")
)

mosquito.RegisterDialog(
	"alice.welcome",
	dialog.New("Hello, my name is alice")
	.Next(
		dialog.New("Welcome to my apple store")
		.Next(dlog)
	)
)
```
## Dialog Tree
Content Here![[dialoger 2022-09-04 15.42.32.excalidraw]]