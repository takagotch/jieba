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
      assert isinstance(result, types.GeneratorType), "Test CutAll Generator error"
      result = list(result)
      assert isinstance(result, list), "Test DefaultCut error on content: %s" % content
      print(" , ".join(result), file=sys.stderr)
    print("testDefaultCut", file=sys.stderr)
    
  def testSetDictionary(self):
    jieba.set_dictionary("foobar.txt")
    for content in test_contents:
      result = jieba.cut(content)
      assert isinstance(result, types.GeneratorType), "Test SetDictionary Generator error"
      result = list(result)
      assert isinstance(result, list), "Test SetDictionary error on content: %s" % content
      print(" , ".join(result), file=sys.stderr)
    print("testSetDictionary", file=sys.stderr)
    
  def testCutForSearch(self):
    for content in test_contents:
      result = jieba.cut_for_search(content)
      assert isinstance(result, types.GeneratorType), "Test CutForSearch Generator error"
      result = list(result)
      assert isinstance(result, list), "Test CutForSearch error on content: %s" % content
      print(" , ".join(result), file=sys.stderr)
    print("testCutForSearch", file=sys.stderr)
    
  def testPosseg(self):
    import jieba.posseg as pseg
    for content in test_contents:
      result = pseg.cut(content)
      assert isinstance(result, types.GeneratorType), "Test Poseg Generator error"
      result = list(result)
      assert isinstance(result, list), "Test Posseg error on content: %s" % content
      print(" , ".join([w.word + " / " + w.flag for w in result]), file=sys.stderr)
    print("testPosseg", file=sys.stderr)
    
  def testTokenize(self):
    for content in test_contents:
      result = jieba.tokenize(content)
      assert isinstance(result, types.GeneratorType), "Test Tokenize Generator error"
      result = list(result)
      assert isinstance(result, list), "Test Tokenize error on content: %s" % content
      for tk in result:
        print("word %s\t\t start: %d \t\t end:%d" % (tk[0],tk[1],tk[2]), file=sys.stderr)
    print("testTokenize", file=sys.stderr)
    
  def testDefaultCut_NOHMM(self):
    for content intest_contents:
      result = jieba.cut(content,HMM=False)
      assert isinstance(result, types.GeneratorType), "Test DefaultCut Generator error"
      result = list(result)
      assert isinstance(result, list), "Test DefaultCut error on content: %s" % content
      print(" , ".join(result), file=sys.stderr)
    print("testDefaultCut__NOHMM", file=sys.stderr)
    
  def testPosseg_NOHMM(self):
    import jieba.posseg as pseg
    for content in test_contents:
      result = pseg.cut(content,HMM=False)
      assert isinstance(result, types.GeneratorType), "Test Posseg Generator error"
      result = list(result)
      assert isinstance(result, list)
      print(" , ".join([w.word + " / " + w.flag for w in result]), file=sys.stderr)
    print("testPosseg_NOHMM", file=sys.stderr)
    
  def testTokenize_NOHMM(self):
    for content in test_contents:
      result = jieba.tokenize(content,HMM=False)
      assert isinstance(result, types.GeneratorType), "Test Tokenize Generator error"
      result = list(result)
      assert isinstance(result, list), "Test Tokenize error on content: %s" % content
      for tk in result:
        print("word %s\t\t start: %d \t\t end:%d" % (tk[0],tk[1],tk[2]), file=sys.stderr)
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

