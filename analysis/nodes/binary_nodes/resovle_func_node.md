## Resolve func node


- used for resolveinterfacefunc, resolvevirtualfunc
- bOpnd[0] stores base vtab/itab address
- bOpnd[1] stores offset

```
class ResolveFuncNode : public BinaryNode {
 public:
  explicit ResolveFuncNode(Opcode o) : BinaryNode(o), puIdx(0) {}

  ResolveFuncNode(Opcode o, PrimType typ) : BinaryNode(o, typ), puIdx(0) {}

  ResolveFuncNode(Opcode o, PrimType typ, PUIdx idx) : BinaryNode(o, typ), puIdx(idx) {}

  ResolveFuncNode(Opcode o, PrimType typ, PUIdx pIdx, BaseNode *opnd0, BaseNode *opnd1)
      : BinaryNode(o, typ, opnd0, opnd1), puIdx(pIdx) {}

 private:
  PUIdx puIdx;
};

```
