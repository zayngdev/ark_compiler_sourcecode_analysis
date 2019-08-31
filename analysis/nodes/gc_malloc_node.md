


```
class GCMallocNode : public BaseNode {
 public:
  explicit GCMallocNode(Opcode o) : BaseNode(o), tyIdx(0), origPrimType(kPtyInvalid) {}

  GCMallocNode(Opcode o, PrimType typ, TyIdx tIdx) : BaseNode(o, typ, 0), tyIdx(tIdx), origPrimType(kPtyInvalid) {}

 private:
  TyIdx tyIdx;
  PrimType origPrimType;
};

```