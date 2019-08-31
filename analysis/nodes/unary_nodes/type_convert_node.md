## Base Node
The node for parser to traverse.

```
class TypeCvtNode : public UnaryNode {
 public:
  explicit TypeCvtNode(Opcode o) : UnaryNode(o), fromPrimType(kPtyInvalid) {}

  TypeCvtNode(Opcode o, PrimType typ) : UnaryNode(o, typ), fromPrimType(kPtyInvalid) {}

  TypeCvtNode(Opcode o, PrimType typ, PrimType fromtyp, BaseNode *expr)
      : UnaryNode(o, typ, expr), fromPrimType(fromtyp) {}

 private:
    PrimType fromPrimType;
  
};
```