


```
class BinaryNode : public BaseNode, public BinaryOpnds {
 public:
  explicit BinaryNode(Opcode o) : BaseNode(o, 2) {}

  BinaryNode(Opcode o, PrimType typ) : BaseNode(o, typ, 2) {}

  BinaryNode(Opcode o, PrimType typ, BaseNode *l, BaseNode *r) : BaseNode(o, typ, 2) {
    SetBOpnd(l, 0);
    SetBOpnd(r, 1);
  }

  bool IsCommutative() const {
      switch (GetOpCode()) {
        case OP_add:
        case OP_mul:
        case OP_band:
        case OP_bior:
        case OP_bxor:
        case OP_land:
        case OP_lior:
          return true;
        default:
          return false;
      }
    }




```