## Base Node
The node for parser to traverse.

```
class BaseNode {
 public:
  explicit BaseNode(Opcode o) {
    op = o;
    ptyp = kPtyInvalid;
    typeflag = 0;
    numopnds = 0;
  }
  
  BaseNode(Opcode o, uint8 numopr) {
    op = o;
    ptyp = kPtyInvalid;
    typeflag = 0;
    numopnds = numopr;
  }
  
  BaseNode(const Opcode o, const PrimType typ, uint8 numopr) {
    op = o;
    ptyp = typ;
    typeflag = 0;
    numopnds = numopr;
  }  

  virtual bool IsLeaf(void);
  virtual bool IsUnaryNode(void);
  virtual bool IsBinaryNode(void);

  virtual void DumpBase(const MIRModule *mod, int32 indent) const;
  
  virtual void Dump(const MIRModule *mod, int32 indent) const {
     DumpBase(mod, indent);
  }

  void Dump(const MIRModule *mod) const {
    Dump(mod, 0);
    LogInfo::MapleLogger() << std::endl;
  }

 protected:
  Opcode op;
  PrimType ptyp;
  uint8 typeflag;  // a flag to speed up type related operations in the VM
  uint8 numopnds;  // only used for N-ary operators, switch and rangegoto
}
```