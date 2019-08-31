


```
class NaryNode : public BaseNode, public NaryOpnds {
 public:
  NaryNode(MapleAllocator *allocator, Opcode o) : BaseNode(o), NaryOpnds(allocator) {}

  NaryNode(const MIRModule *mod, Opcode o) : NaryNode(mod->CurFuncCodeMemPoolAllocator(), o) {}

  NaryNode(MapleAllocator *allocator, Opcode o, PrimType typ) : BaseNode(o, typ, 0), NaryOpnds(allocator) {}

  NaryNode(const MIRModule *mod, Opcode o, PrimType typ) : NaryNode(mod->CurFuncCodeMemPoolAllocator(), o, typ) {}

  NaryNode(MapleAllocator *allocator, const NaryNode *node)
      : BaseNode(node->GetOpCode(), node->GetPrimType(), node->numopnds), NaryOpnds(allocator) {}

  NaryNode(const MIRModule *mod, const NaryNode *node) : NaryNode(mod->CurFuncCodeMemPoolAllocator(), node) {}


```