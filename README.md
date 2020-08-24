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

### 描画

```python
import matplotlib.pyplot as plt
plt.figure(figsize=(12,12))
plt.axis("equal)

#pos :: position
#nodelist :: 描画する点
#edgelist :; 描画する枝(枝を出さない場合は[]を渡す)
nx.draw_networkx(G, pos=C, nodelist=G.nodes(), edgelist=G.edges())
plt.show()
```

### 最小木を求める
```python
T = nx.minimum_spanning_tree(G)
print("size of MST:", T.size(weight="weight"))

#最小木で選ばれた枝を出力
for e in T.edges():
    print(e)
```

### 最小木の描画
```python
plt.figure(figsize=(12,12))
nx.draw_networkx(T, pos=C)
plt.show()
```