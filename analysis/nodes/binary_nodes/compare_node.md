
```
class CompareNode : public BinaryNode {
 public:
  explicit CompareNode(Opcode o) : BinaryNode(o), opndType(kPtyInvalid) {}

  CompareNode(Opcode o, PrimType typ) : BinaryNode(o, typ), opndType(kPtyInvalid) {}

  CompareNode(Opcode o, PrimType typ, PrimType otype, BaseNode *l, BaseNode *r)
      : BinaryNode(o, typ, l, r), opndType(otype) {}

 private:
  PrimType opndType;  // type of operands.
};

```