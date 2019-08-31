## Unary Node
Single operand

```
class UnaryNode : public BaseNode {
 public:
    explicit UnaryNode(Opcode o) : BaseNode(o, 1), uOpnd(nullptr) {}
    
    UnaryNode(Opcode o, PrimType typ) : BaseNode(o, typ, 1), uOpnd(nullptr) {}
    
    UnaryNode(Opcode o, PrimType typ, BaseNode *expr) : BaseNode(o, typ, 1), uOpnd(expr) {}

 private:
  BaseNode *uOpnd;
}
```