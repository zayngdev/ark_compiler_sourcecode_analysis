
```
lass DepositbitsNode : public BinaryNode {
 public:
  DepositbitsNode() : BinaryNode(OP_depositbits), bitsOffset(0), bitsSize(0) {}

  DepositbitsNode(Opcode o, PrimType typ) : BinaryNode(o, typ), bitsOffset(0), bitsSize(0) {}

  DepositbitsNode(Opcode o, PrimType typ, uint8 offset, uint8 size, BaseNode *l, BaseNode *r)
      : BinaryNode(o, typ, l, r), bitsOffset(offset), bitsSize(size) {}

 private:
  uint8 bitsOffset;
  uint8 bitsSize;
};
```