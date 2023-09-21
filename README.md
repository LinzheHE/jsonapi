# jsonapi

Project purpose: extend the json api to make it support encode and decode for complex and range.

To install the api, in terminal run:
pip install extendjsonapi

To use the extended json api, at the beginning in you python file:
```
from extendjsonapi import *
import json
```

To use the the encoder for complex or range:
```
json.dumps(obj, cls=MyEncoder)
```

To use the decoder for complex or range:
```
json.loads(obj, cls=MyDecoder)
```

>*NOTICE: since jsonapi is already used on PyPI, update the api name to extendjsonapi*
>
>*setup.py is not included since this api is built using poetry, all set up information are included in the pyproject.toml*

you can run the following code to test whether it works or not:
```
from extendjsonapi import *
import pytest
import json

def test_encoded():
    test_complex = complex(1, 2)

    encoded_complex = json.dumps(test_complex, cls=MyEncoder)
    decoded_complex = json.loads(encoded_complex, cls=MyDecoder)

    assert decoded_complex == test_complex

def test_decoded():
    test_range = range(1, 10, 3)

    encoded_range = json.dumps(test_range, cls=MyEncoder)
    decoded_range = json.loads(encoded_range, cls=MyDecoder)
    
    assert decoded_range == test_range
