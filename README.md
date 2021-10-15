# IOC Fanger

[![PyPi](https://img.shields.io/pypi/v/ioc_fanger.svg)](https://pypi.python.org/pypi/ioc_fanger)
![PyPI - Downloads](https://img.shields.io/pypi/dm/ioc-fanger)
[![Travis CI](https://img.shields.io/travis/ioc-fang/ioc_fanger.svg)](https://travis-ci.org/ioc-fang/ioc_fanger)
[![Codecov](https://codecov.io/gh/ioc-fang/ioc_fanger/branch/master/graph/badge.svg)](https://codecov.io/gh/ioc-fang/ioc_fanger)
[![live demo](https://img.shields.io/badge/live%20demo-%E2%86%92-green)](http://ioc-fanger.hightower.space/)

Python package to fang and defang [indicators of compromise](https://digitalguardian.com/blog/what-are-indicators-compromise) in text.

```python
import ioc_fanger

ioc_fanger.defang("example.com http://bad.com/phishing.php")  # example[.]com hXXp://bad[.]com/phishing[.]php
ioc_fanger.fang("example[.]com hXXp://bad[.]com/phishing[.]php")  # example.com http://bad.com/phishing.php
```

**Defanging** - converting indicators of compromise from the normal form (which can become links) to a form which cannot accidentally become a link:

`example.com => example[.]com`

**Fanging** - converting indicators of compromise from a defanged form to the normal, original form:

`example[.]com => example.com`

**What can it fang?**

Just about everything. Check out the [tests](https://github.com/ioc-fang/ioc_fanger/blob/master/tests/test_ioc_fanger.py) to see some examples of what this package can handle.
