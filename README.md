## Depth First Search

Depth First Search (DFS) adalah suatu metode pencarian pada sebuah 
pohon dengan menelusuri satu cabang sebuah pohon sampai menemukan solusi. 
Pencarian dilakukan pada satu node dalam setiap level

penjelasan program :

pendeklarasian class dan constructor

```
class Graph:
    # Constructor
    def __init__(self):
        # default dictionary to store graph
        self.graph = defaultdict(list)
 ```
 addEdge(), untuk menambahkan node pada graph
 
 ```
    def addEdge(self, u, v):
        self.graph[u].append(v)
 ```
 DFSUtil(), fungsi rekursif digunakan untuk mengecek dan menentukan node yang telah/belum di cek
 jika belum di cek maka fungsi akan memanggil dirinya sendiri
 
 ```
    def DFSUtil(self, v, visited):
        visited.add(v)
        print(v, end=' ')
        for neighbour in self.graph[v]:
            if neighbour not in visited:
                self.DFSUtil(neighbour, visited)
 ```
 DFS(), fungsi untuk menjalankan program
 
 ```
    def DFS(self, v):
        visited = set()
        self.DFSUtil(v, visited)
 ```
