# Py-GoogleTrans

[![Build Status](https://travis-ci.org/ssut/py-googletrans.svg?branch=master)](https://travis-ci.org/ssut/py-googletrans)
[![Documentation Status](https://readthedocs.org/projects/py-googletrans/badge/?version=latest)](https://readthedocs.org/projects/py-googletrans/?badge=latest)
[![PyPI version](https://badge.fury.io/py/py-googletrans.svg)](http://badge.fury.io/py/py-googletrans)

Py-GoogleTrans is a Python library that translates the text you want to translate using Google Translate.

Compatible with Python 2.7 and 3.4 (cPython and PyPy. Py 2.6 and 3.3 are not tested yet.)

For details refer to the [API Documentation](https://py-googletrans.readthedocs.org/en/latest/googletrans.html).

---

## Installation

To install, either use things like pip with the package "py-googletrans" or download the package and put the "googletrans" directory into your python path.

```bash
$ pip install py-googletrans
```

### Requirements

- requests
- future

---

## Basic Usage

```python
>>> from googletrans import translator
>>> translator.translate('안녕하세요.')
# <Translated src=ko dest=en text=Good evening. pronunciation=Good evening.>
>>> translator.translate('안녕하세요.', dest='ja')
# <Translated src=ko dest=ja text=こんにちは。 pronunciation=Kon'nichiwa.>
>>> translator.translate('veritas lux mea', src='la')
# <Translated src=la dest=en text=The truth is my light pronunciation=The truth is my light>
```

### Advanced Usage (Batch)

```python
>>> translations = translator.translate(['The quick brown fox', 'jumps over', 'the lazy dog'], dest='ko')
>>> for translation in translations:
...    print(translation.origin, ' -> ', translation.text)
# The quick brown fox  ->  빠른 갈색 여우
# jumps over  ->  이상 점프
# the lazy dog  ->  게으른 개
```

---

## A note on library usage

Due to limitations of Google Translate, this API does not guarantee that the library would work properly. (please use this library if you don't care about stability.)

If you want to a stable, I recommend you to use [Google's official translate API](https://cloud.google.com/translate/docs).

---

## Submitting a Pull Request

1. Fork this project.
2. Create a topic branch.
3. Implement your feature or bug fix.
4. Run `python tests.py` or `python -m unittest -v`.
5. Add a test for yout feature or bug fix.
6. Run step 4 again. If your changes are not 100% covered, go back to step 5.
7. Commit and push your changes.
8. Submit a pull request.

---

## License

Py-GoogleTrans is licensed under the MIT License. The terms are as follows:

```
The MIT License (MIT)

Copyright (c) 2015 SuHun Han

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```