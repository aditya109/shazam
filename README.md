# shazam ⚡️
Just a safe and better http to curl for golang
--------

`shazam` is a plugin which is used to print curl for your HTTP requests, in pre-flight scenarios.
The word safe is used here, as `shazam` implements a naïve technique to protect sensitive request pointers.

## How to get started ?

1. Import `shazam` in your code.
    ```
    go get github.com/Kieraya/shazam
    ```
    
2. Add the following to your code.
    ```golang
    ...
        request, err := http.NewRequest(http.MethodGet, url, nil)
        // handle error
        curl, err := shazam.Boom(request)
        if err != nil {
            log.Println(err)
        }
        log.Println(curl)
    ..
    ```
    That's it ! You should see something like this:

    ```bash
    curl --location --request GET 'https://reqres.in/api/users?page=2' --header 'x-panem-token: BUM99779r42aUZUZB8Z95YLK'
    ```

Thanks and have fun. Happy hacking !
