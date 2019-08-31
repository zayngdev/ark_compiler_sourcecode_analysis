## Base Node
Retype node

```
class RetypeNode : public TypeCvtNode {
 public:
  RetypeNode() : TypeCvtNode(OP_retype), tyIdx(0) {}

  explicit RetypeNode(PrimType typ) : TypeCvtNode(OP_retype, typ), tyIdx(0) {}

 private:
  TyIdx tyIdx;
};
```
