## Synopsis

Support files to build python data science docker image.

## Code Example

Bash function to run ipython shell or jupyter notebook.

```bash
dipy() {
    image=ianfang/pydata
    docker run -v $PWD:/tmp/working -w=/tmp/working --rm -it $image ipython
}
djup() {
    image=ianfang/pydata
    docker run -v $PWD:/tmp/working -w=/tmp/working -p 8888:8888 --rm -it $image jupyter notebook --no-browser --ip="*" --notebook-dir=/tmp/working
}
```

## Motivation

Create an isolated and portable python based data science development environment.

## Installation

docker build -t <tag> .

## API Reference

None

## Tests

None

## Contributors

Ian Fang, xingang.fang@gmail.com

## License

Public

## TODO
    Combine ENV into RUN command
