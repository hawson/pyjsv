pyjsv
=====
Quick and dirty python object to implement the JSV api for UGE/S(o)GE script verifcation.

When you create your own JSV, import the jsv and subclass your jsv object to the master. override the ```jsv_on_verify``` and/or the ```jsv_on_start``` functions. I haven't tested env handling yet, but everything else seems to work. Should work in both python2 and python3, and I've no reason to believe it shouldn't work in pypy or other python interpreters.

```python
from JSV import JSV
class MyJSV(JSV):
  def jsv_on_verify(self):
    self.jsv_accept("")
    
j = MyJSV()
j.jsv_main()
```

This does no inherent type introspection, all ```jsv_(sub_)?get_``` operations will return strings and/or dictionaries. cast them if necessary.
