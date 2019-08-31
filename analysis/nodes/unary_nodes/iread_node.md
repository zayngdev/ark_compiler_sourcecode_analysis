

```


class IreadoffNode : public UnaryNode {

  IreadoffNode() : UnaryNode(OP_ireadoff), offset(0) {}
 
   IreadoffNode(PrimType ptyp, int32 ofst) : UnaryNode(OP_ireadoff, ptyp), offset(ofst) {}

 private:
  int32 offset;
};


```