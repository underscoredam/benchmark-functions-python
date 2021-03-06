# benchmark-functions-python
Compare multiple Python functions and statistically compare their speeds

![Screenshot](/screenshot.png)

## Interpreter support
* Python 3
* Python 2
* ~PyPy~ (`scipy` is incompatible with `PyPy`)

## Requirements and Installation
* Install Python and [`virtualenv`](https://virtualenv.pypa.io/en/stable/). Then run the following:
``` bash
#/bin/bash
cd <directory>
virtualenv bfs
source bfs/bin/activate
pip install -r requirements.txt

# To run the program, 
python main.py

# And whenever you're done using the software
deactivate
```

## Use cases
Suppose you have a specific kind of dataset and you want to compare the efficiency of various sorting algorithms. You want to know whether binary trees are better worse than hashtables. You want to compare which implementation of code is faster, or maybe what runs faster *on* Python. If you have that kind of need then this repo is for you.

As an example, [functions.py](/functions.py) contains various implementations of [insertion sort algorithm](https://en.wikipedia.org/wiki/Insertion_sort). For most part, they are the same but each of them contains a crucial difference which marks the thing that we want to compare.

## Statistical approaches
* Compute mean and variance
* Compte z-score.
* Visual representation of data (uncommend [this](https://github.com/underscoredam/benchmark-functions-python/blob/master/main.py#L80) line).
* Outlier fix. Anything not within -OUTLIER\_MARGIN \< z\-score  \< +OUTLIER\_MARGIN is considered an outlier.
* 1\-way ANOVA is used to calculate t\* score and p-value. 

## Tips
* The more the p-value, the more likely that the functions perform similarly.
* The lesser the p-value, the more likely that one founction outperforms another.
* Don't forget to read the annotations for `compare()` in `main.py`. 
* And if you want to run the batch processor (`runner.bash`), change the second range of `runner.bash`, from `0` to the total number of tests that you're running.

## Author
Damodar Dahal

## License
The MIT License.
