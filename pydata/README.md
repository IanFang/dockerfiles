## Synopsis

Support files to build python data science (including cheminformatics) docker image.
Packages:

> Python: Python 2.7, iPython, Jupyter notebook, Nose, Pytest
> Scientific: Numpy, Scipy, Matplotlib, Seaborn, Scikit image
> Machine learning: Scikit Learn, Tensorflow, Keras, Theano, Xgboost
> Cheminformatics: openbabel, rdkit
> Other: PySpectral

## Code Example

Bash function to run ipython shell or jupyter notebook with the current directory mapped as the working directory.

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

docker build -t \[tag\] .

## API Reference

None

## Tests

None

## Contributors

Ian Fang

## License

Public

