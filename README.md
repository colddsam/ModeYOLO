# ModeYOLO Python Package

## Introduction
ModeYOLO is a Python package designed to perform color space transformations on images and facilitate the creation of modified datasets for training deep learning models. The package consists of two main modules: `ColorOperation.py` and `Operation.py`. 

### Folder Structure
Before using the package, ensure that your source dataset follows the following folder structure:

```plaintext
dataset/
|-- train/
|   |-- images/
|   |-- labels/
|-- test/
|   |-- images/
|   |-- labels/
|-- val/
|   |-- images/
|   |-- labels/
|-- data.yaml
```

## ColorOperation Module (`ColorOperation.py`)

### Class: `colorcng`

#### Constructor
```python
def __init__(self, path: str, mode: str = 'all') -> None:
    """
    Initializes the colorcng object.

    Parameters:
    - path: str, path to the target directory.
    - mode: str, mode of operation ('all', 'rgb', 'bgr', 'gray', 'hsv', 'crcb', 'lab').
    """
```

#### Methods
1. `cng_rgb`
    ```python
    def cng_rgb(self, opt: str, img: np.ndarray, idx: int | str = 0) -> None:
        """
        Converts the image to RGB color space.

        Parameters:
        - opt: str, operation type ('train', 'test', 'val').
        - img: np.ndarray, input image.
        - idx: int | str, index for the output file name.
        """
    ```

2. `cng_bgr`
    ```python
    def cng_bgr(self, opt: str, img: np.ndarray, idx: int | str = 0) -> None:
        """
        Saves the image in BGR color space.

        Parameters:
        - opt: str, operation type ('train', 'test', 'val').
        - img: np.ndarray, input image.
        - idx: int | str, index for the output file name.
        """
    ```

3. `cng_gray`
    ```python
    def cng_gray(self, opt: str, img: np.ndarray, idx: int | str = 0) -> None:
        """
        Converts the image to grayscale.

        Parameters:
        - opt: str, operation type ('train', 'test', 'val').
        - img: np.ndarray, input image.
        - idx: int | str, index for the output file name.
        """
    ```

4. `cng_hsv`
    ```python
    def cng_hsv(self, opt: str, img: np.ndarray, idx: int | str = 0) -> None:
        """
        Converts the image to HSV color space.

        Parameters:
        - opt: str, operation type ('train', 'test', 'val').
        - img: np.ndarray, input image.
        - idx: int | str, index for the output file name.
        """
    ```

5. `cng_crcb`
    ```python
    def cng_crcb(self, opt: str, img: np.ndarray, idx: int | str = 0) -> None:
        """
        Converts the image to YCrCb color space.

        Parameters:
        - opt: str, operation type ('train', 'test', 'val').
        - img: np.ndarray, input image.
        - idx: int | str, index for the output file name.
        """
    ```

6. `cng_lab`
    ```python
    def cng_lab(self, opt: str, img: np.ndarray, idx: int | str = 0) -> None:
        """
        Converts the image to LAB color space.

        Parameters:
        - opt: str, operation type ('train', 'test', 'val').
        - img: np.ndarray, input image.
        - idx: int | str, index for the output file name.
        """
    ```

7. `execute`
    ```python
    def execute(self, opt: str, file: str, idx: int | str = 0) -> None:
        """
        Executes the specified color space transformation.

        Parameters:
        - opt: str, operation type ('train', 'test', 'val').
        - file: str, path to the input image.
        - idx: int | str, index for the output file name.
        """
    ```

## Operation Module (`Operation.py`)

### Class: `InitOperation`

#### Constructor
```python
def __init__(self, target_directory: str = 'modified_dataset', src_directory: str = 'dataset', mode: str = 'all') -> None:
    """
    Initializes the InitOperation object.

    Parameters:
    - target_directory: str, path to the target directory.
    - src_directory: str, path to the source dataset directory.
    - mode: str, mode of operation ('all', 'rgb', 'bgr', 'gray', 'hsv', 'crcb', 'lab').
    """
```

#### Methods
1. `start_train`
    ```python
    def start_train(self) -> None:
        """
        Creates the modified training dataset.
        """
    ```

2. `start_test`
    ```python
    def start_test(self) -> None:
        """
        Creates the modified testing dataset.
        """
    ```

3. `start_val`
    ```python
    def start_val(self) -> None:
        """
        Creates the modified validation dataset.
        """
    ```

4. `reform_dataset`
    ```python
    def reform_dataset(self) -> None:
        """
        Reformats the entire dataset.
        """
    ```

### Example Usage

```python
# Import the InitOperation class
from ModeYOLO.Operation import InitOperation

# Create an InitOperation object
init_op = InitOperation(target_directory='modified_dataset', src_directory='dataset', mode='all')

# Create the modified dataset
init_op.reform_dataset()
```

This example assumes that the source dataset is structured according to the specified folder structure. Adjust the paths and parameters accordingly based on your dataset structure.