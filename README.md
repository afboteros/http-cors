# http-cors
CORS Basic Handler for http/net in Go

## Installation

``` bash
$ go get github.com/afboteros/http-cors
```

## Usage

``` go
import (
    "github.com/afboteros/http-cors"
)

func main() {
    /**
     * Create some Handlers, Handlers must be added for each HandlerFunc
     * and CORS must be added to the Handlers as needed
     */
	genericHandler := http.HandlerFunc(genericHandler)
    http.Handle("/", cors.CorsHandler(cors.Options{}, genericHandler))
    // Initialize the server
    log.Println("Server initializated at port 3000")
    log.Println(http.ListenAndServe(":3000", nil))
}

func genericHandler(res http.ResponseWriter, req *http.Request) {
	res.Write([]byte("Hello World!")
}
```

## AngularJS OPTIONS Management
When working with AngularJS ngResource, Options method will return error with some libraries, due to status return on this method
``` go
if r.Method == OptionsMethod {
    w.WriteHeader(http.StatusNoContent)
}
```