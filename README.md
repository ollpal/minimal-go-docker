# A minimal docker image based on a go binary

information from <https://blog.codeship.com/building-minimal-docker-containers-for-go-applications/>

## Building the go binary

### Power-shell

    $Env:CGO_ENABLED = 0
    $Env:GOOS = "linux"
    go build -a -installsuffix cgo -o main .

## Building the docker image

    docker build -f Dockerfile -t minimal:latest .

## Running the docker image

    docker run --rm -it minimal

or if behind a proxy

    docker run --rm -it -e http_proxy=<proxy> minimal