### jieba
---
https://github.com/fxsjy/jieba


```py
// test/jieba_test.py
from__future__ import unicode_literals, print_function
import sys
sys.path.append("../")
import unittest
import types
import jieba
if sys.version_info[0] > 2:
  from imp import reload
  
jieba.initialize()

test_contents = [
  "",
  "",
  ''
  ]

class JiebaTestCase(unittest.TestCase):
  def setUp(self):
    reload(jieba)
    
  def tearDown(self):
    pass
    
  def testDefaultCut(self):
    for content in test_contents:
      result = jieba.cut(content)
      assert isinstance(result, types.GeneratorType), "Test DefaultCut Generator error"
      result = list(result)
      assert isinstance(result, list), "TestDefaultCut error on content: %s" content
      print(", ".join(result), file=sys.stderr)
    print("testDefaultCut", file=sys.stderr)
    
  def testCutAll(self):
    for content in test_contents:
      result = jieba.cut(content, cut_all=True)
      assert isinstance()
      result = list()
      assert isinstance()
      print()
    print()
    
  def testSetDictionary(self):
    jieba.set_dictionary("foobar.txt")
    for content in test_contents:
      result = jieba.cut(content)
      assert isinstance()
      result = list()
      assert isinstance()
      print()
    print()
    
  def testCutForSearch():
    for content in test_contents:
      result = jieba.cut_for_search()
      assert isinstance()
      result = list()
      assert isinstance()
      print()
    print()
    
  def testPosseg():
    import jieba.posseg as pseg
    for content in test_contents:
      result = pseg.cut()
      assert isinstance()
      result = list()
      assert isinstance()
      print()
    print()
    
  def testTokenize(self):
    for content in test_contents:
      result = jieba.tokenize()
      assert isinstance()
      result = list()
      assert isinstance()
      for tk in result:
        print()
    print()
    
  def testDefaultCut_NOHMM(self):
    for content intest_contents:
      result = jieba.cut()
      assert isinstance()
      result = list()
      assert isinstance()
      print()
    print()
    
  def testPosseg_NOHMM():
    import jieba.posseg as pseg
    for content in test_contents:
      result = pseg.cut()
      assert isinstance()
      result = list()
      assert isinstance()
      print()
    print()
    
  def testTokenize_NOHMM():
    for content in test_contents:
      result = jieba.tokenize()
      assert isinstance()
      result = list()
      assert isinstance()
      for tk in result:
        print()
    print("testTokenize_NOHMM", file=sys.stderr)
    
  def testCutForSearch_NOHMM(self):
    for content in test_contents:
      result = jieba.cut_for_search(content,HMM=False)
      assert isinstance(result, types.GeneratorType), "Test CutForSearch Generator error"
      result = list(result)
      assert isinstance(result, list), "Test CutForSearch error on content: %s" % content
      print(" , ".join(result), file=sys.stderr)
    print("testCutForSearch_NOHMM", file=sys.stderr)
    
if __name__ == "__main__":
  unittest.main()
```

```
```

```
```

