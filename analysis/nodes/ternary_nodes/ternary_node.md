## Ternary Node

```
class TernaryNode : public BaseNode {
 public:
  explicit TernaryNode(Opcode o) : BaseNode(o, 3) {
    topnd[0] = nullptr;
    topnd[1] = nullptr;
    topnd[2] = nullptr;
  }

  TernaryNode(Opcode o, PrimType typ) : BaseNode(o, typ, 3) {
    topnd[0] = nullptr;
    topnd[1] = nullptr;
    topnd[2] = nullptr;
  }

  TernaryNode(Opcode o, PrimType typ, BaseNode *e0, BaseNode *e1, BaseNode *e2) : BaseNode(o, typ, 3) {
    topnd[0] = e0;
    topnd[1] = e1;
    topnd[2] = e2;
  }
   
  TernaryNode *CloneTree(MapleAllocator *allocator) const {
    TernaryNode *nd = allocator->GetMemPool()->New<TernaryNode>(*this);
    nd->topnd[0] = topnd[0]->CloneTree(allocator);
    nd->topnd[1] = topnd[1]->CloneTree(allocator);
    nd->topnd[2] = topnd[2]->CloneTree(allocator);
    return nd;
  }

 private:
  BaseNode *topnd[3];
};

```