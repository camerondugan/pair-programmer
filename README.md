# Pair Programmer

An LLM for helping with code fast while not doing it for you, allowing you to
learn in the process. Other models will give you code outright, and avoid
explaining unless you prompt it to. This model is for use in code/text editors
with plugins that support Ollama.

## Expected use examples:

>>> what's wrong with this code? "print('hello world)"

The code is missing a closing parenthesis after the string. It should be "print('hello world')"

---

>>> write me a go server

You must learn, I cannot write code for you. However, I can provide you with some guidance on how to create a Go server.

1. First, make sure you have Go installed on your computer. You can download the latest version from the official Go website.
2. Create a new directory for your project and navigate to it in your terminal or command prompt.
3. Use the `go mod init` command to initialize your module. This will create a `go.mod` file that contains information about your module, including its
name and version.
4. Create a new file called `main.go` in your project directory. This is where you'll write your server code.
5. In the `main.go` file, import the necessary packages for your server. For example:

```Go
import (
	"fmt"
	"net/http"
)
```

6. Create a new function called `handleRequest` that will handle incoming HTTP requests. This function should take an `http.Request` object as its
argument and return an `http.Response` object. For example:

```Go
func handleRequest(w http.ResponseWriter, r *http.Request) {
	fmt.Fprintf(w, "Hello, world!")
}
```

7. In the `main` function, create a new instance of an `http.Server` and set its `Handler` field to the `handleRequest` function you just created. For
example:

```Go
func main() {
	server := &http.Server{
		Addr:    ":8080",
		Handler: handleRequest,
	}
	log.Fatal(server.ListenAndServe())
}
```

This code will start an HTTP server on port 8080 and listen for incoming requests. When a request is received, it will call the `handleRequest` function
to handle it. The `handleRequest` function will return an `http.Response` object with the string "Hello, world!" as its body.

I hope this helps! Let me know if you have any questions or need further assistance.

---

>>> give me a crud application
I'm happy to help you with your CRUD (Create, Read, Update, Delete) application! However, I would like to point out that creating a full-fledged CRUD
application can be a complex task and may require a lot of code. It's important to have a clear understanding of the problem you are trying to solve
before starting to write any code.

To get started, let's first define what we mean by "CRUD" in this context. Can you tell me more about the problem you are trying to solve and what
features your CRUD application should have? This will help us determine the best approach for building your application.

>>> I want to have a website where you can chat with a bot
That sounds like an interesting project! To create a website that allows users to chat with a bot, you'll need to use a combination of HTML, CSS, and
JavaScript. Here are the basic steps you can follow:

1. Create an HTML file that includes a form for the user to input their message and a div element where the bot's response will be displayed.
2. Use CSS to style the page and make it look presentable.
3. Write JavaScript code that listens for the user's input and sends it to the bot. You can use a library like `axios` or `fetch` to send HTTP requests to
your bot's API endpoint.
4. When the bot responds, update the div element with the response from the bot.
5. Test your website by opening it in a web browser and sending some messages to the bot.

Remember that this is just a basic outline of how you can create a chatbot website. Depending on the complexity of your project, you may need to add more
features or use different technologies. Good luck with your project!

## Setup

Before use, it's recommended to ensure you have a GPU setup for ML.

```bash
# get these files
git clone https://github.com/camerondugan/pair-programmer.git
cd pair-programmer
# download the model
ollama create -f pair-programmer.ModelFile pair-programmer
# run the model
ollama run pair-programmer
```
