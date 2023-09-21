# jsonapi

Project purpose: extend the json api to make it support encode and decode for complex and range.

To use the extended json api:
from extendjsonapi import *
import json

To use the the encoder:
json.dumps(obj, cls=MyEncoder)

To use the decoder:
json.loads(obj, cls=MyDecoder)

*NOTICE: since jsonapi is already used on PyPI, update the api name to extendjsonapi*