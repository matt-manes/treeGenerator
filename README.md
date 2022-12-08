# treeGenerator<br>
Install with <pre>python -m pip install git+https://github.com/matt-manes/treegenerator</pre>
Git needs to be installed and in your PATH.<br>
<br>
Contains two classes: TreeGenerator and UrlTreeGenerator.<br>
TreeGenerator takes a local file path and recursively generates a tree representation of all subdirectories.<br>
UrlTreeGenerator takes a list of urls and generates a tree representation of them.<br>
<br>
Usage:<br>
<pre>
from treeGenerator import TreeGenerator
from pathlib import Path
generator = TreeGenerator(Path.cwd())
print(generator)
</pre>
produces<br>
<pre>
treeGenerator
|  |-dist
|  |  |-treegenerator-0.0.1-py3-none-any.whl
|  |  |_treegenerator-0.0.1.tar.gz
|  |
|  |-pyproject.toml
|  |-src
|  |  |-treeGenerator
|  |  |  |-__init__.py
|  |  |  |_treeGenerator.py
</pre>
The dictionary representing the tree can be accessed through the 'tree' member.<br>
<pre>
import json
print(json.dumps(generator.tree, indent=1))
</pre>
produces<br>
<pre>
{
 "treeGenerator": {
  "dist": {
   "treegenerator-0.0.1-py3-none-any.whl": {},
   "treegenerator-0.0.1.tar.gz": {}
  },
  "pyproject.toml": {},
  "src": {
   "treeGenerator": {
    "__init__.py": {},
    "treeGenerator.py": {}
   }
  }
 }
}
</pre>
