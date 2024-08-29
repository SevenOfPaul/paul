```
const level: number = 10
class TNode {
val: number
next: TNode[] = new Array(level)
constructor(_val: number) {
this.val = _val
}
}
class Skiplist {
he: TNode = new TNode(-1)
find(t: number): Array {
let cur = this.he
let ns: TNode[] = new Array(level)
for (let i = level - 1; i >= 0; i--) {
while (cur.next[i] != null && cur.next[i].val < t){
cur = cur.next[i];
}
ns[i] = cur;
}
return ns
}
search(t: number): boolean {
let ns= this.find(t)
return ns[0].next[0] != null && ns[0].next[0].val == t
}
add(t: number): void {
let ns= this.find(t)
const node = new TNode(t)
for (let i = 0; i < level; i++) {
node.next[i] = ns[i].next[i]
ns[i].next[i] = node
if (Math.round(Math.random()) == 0) break
}
}
erase(t: number): boolean {
let ns= this.find(t)
const node = ns[0].next[0]
if (node == null || node.val != t) return false
for (let i = 0; i < level && ns[i].next[i] == node; i++) ns[i].next[i] = ns[i].next[i].next[i]
return true
}
}
```