# excercise_logistics

C : 都市の座標 (x, y)
n : 都市の数

distance関数 : ２つの都市の距離を返す

### networkx

```python
import networkx as nx
#グラフの作成
G = nx.Graph()

#グラフに各都市の座標を追加
for v in C:
    G.add_node(v)

#枝を追加
for i, ci in enumerate(C):
    for j, cj in enumerate(C):
        if i < j:
            G.add_edge(ci,cj, weight=distance(C[ci], C[cj]))
```

