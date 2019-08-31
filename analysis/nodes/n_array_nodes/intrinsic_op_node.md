

```
class IntrinsicopNode : public NaryNode {
 public:
  explicit IntrinsicopNode(MapleAllocator *allocator, Opcode o, TyIdx typeIdx = TyIdx())
      : NaryNode(allocator, 0), intrinsic(INTRN_UNDEFINED), tyIdx(typeIdx) {}

  explicit IntrinsicopNode(const MIRModule *mod, Opcode o, TyIdx typeIdx = TyIdx())
      : IntrinsicopNode(mod->CurFuncCodeMemPoolAllocator(), o, typeIdx) {}

  IntrinsicopNode(MapleAllocator *allocator, Opcode o, PrimType typ, TyIdx typeIdx = TyIdx())
      : NaryNode(allocator, o, typ), intrinsic(INTRN_UNDEFINED), tyIdx(typeIdx) {}

  IntrinsicopNode(const MIRModule *mod, Opcode o, PrimType typ, TyIdx typeIdx = TyIdx())
      : IntrinsicopNode(mod->CurFuncCodeMemPoolAllocator(), o, typ, typeIdx) {}

  IntrinsicopNode(MapleAllocator *allocator, const IntrinsicopNode *node)
      : NaryNode(allocator, node), intrinsic(node->GetIntrinsic()), tyIdx(node->GetTyIdx()) {}

  IntrinsicopNode(const MIRModule *mod, const IntrinsicopNode *node)
      : IntrinsicopNode(mod->CurFuncCodeMemPoolAllocator(), node) {}

private:
  TyIdx tyIdx;
};

```