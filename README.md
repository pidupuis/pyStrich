pyStrich
========
pyStrich is a Python module to generate 1D and 2D barcodes. Currently it
supports

 * code39
 * code128
 * ean13
 * datamatrix
 * qrcode - see [known issues](#known-issues)

Available from PyPI: https://pypi.python.org/pypi/pyStrich
 
[![Build Status](https://travis-ci.org/mmulqueen/pyStrich.svg)](https://travis-ci.org/mmulqueen/pyStrich)

Usage
-----
The interface of the different encoders is fairly straightforward:

```python
from pystrich.datamatrix import DataMatrixEncoder
encoder = DataMatrixEncoder("This is a DataMatrix.")
encoder.save( "sample_barcodes/datamatrix_test.png" )
print(encoder.get_ascii())
```
![Sample of DataMatrix generated by the code above.](sample_barcodes/datamatrix_test.png)

Relevant imports are:

```python
from pystrich.code39 import Code39Encoder
from pystrich.code128 import Code128Encoder
from pystrich.datamatrix import DataMatrixEncoder
from pystrich.ean13 import EAN13Encoder
from pystrich.qrcode import QRCodeEncoder
```

Known Issues
----------
Code39, Code128 and DataMatrix support is considered by the maintainer to be good and they are known to be used in 
production.

The maintainer rarely uses EAN13 or QRCode support. You may wish to consider more actively maintained modules. 

The maintainer has no plans to fix the following issues:

* Some QR codes cause an exception to be thrown - root cause unknown - [see issue 8](https://github.com/mmulqueen/pyStrich/issues/8).
* DataMatrix module only supports up to 174 characters or 348 digits of data - [see issue 2](https://github.com/mmulqueen/pyStrich/issues/2).

Background
----------
pyStrich is a fork of huBarcode module with modifications to support Python 3 (amongst other changes). pyStrich
only supports encoding not decoding.

[huBarcode](https://github.com/hudora/huBarcode) was developed by [HuDoRa](http://www.hudora.de/en/) from at least 2007, the project does not seem to have been
active since late 2013. [Method B Ltd](http://method-b.uk) has forked it to provide Python 3 support and facilitate
future development. Thank you to the folks at HuDoRa for doing most of the hard work, porting was the easy part.

License
-------
If you worry about copyright you might consider this Software BSD-Licensed.
If you are still worried, you might consider it GPL1/2/3 compatible.
But don't worry. If you need something formal:
The code is available under the Apache License, Version 2.0.
