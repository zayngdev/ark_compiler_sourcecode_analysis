


```
class ExtractbitsNode : public UnaryNode {
 public:
  explicit ExtractbitsNode(Opcode o) : UnaryNode(o), bitsOffset(0), bitsSize(0) {}

  ExtractbitsNode(Opcode o, PrimType typ) : UnaryNode(o, typ), bitsOffset(0), bitsSize(0) {}

  ExtractbitsNode(Opcode o, PrimType typ, uint8 offset, uint8 size)
      : UnaryNode(o, typ), bitsOffset(offset), bitsSize(size) {}

  ExtractbitsNode(Opcode o, PrimType typ, uint8 offset, uint8 size, BaseNode *expr)
      : UnaryNode(o, typ, expr), bitsOffset(offset), bitsSize(size) {}

 private:
  uint8 bitsOffset;
  uint8 bitsSize;
};

```