


```

class BinaryOpnds {
 public:
  virtual ~BinaryOpnds() = default;

  virtual void Dump(const MIRModule *mod, int32 indent) const;

  BaseNode *GetBOpnd(int32 i) const {
    CHECK_FATAL(i >= 0 && i < 2, "Invalid operand idx in BinaryOpnds");
    return bOpnd[i];
  }

  void SetBOpnd(BaseNode *node, int32 i) {
    CHECK_FATAL(i >= 0 && i < 2, "Invalid operand idx in BinaryOpnds");
    bOpnd[i] = node;
  }

 private:
  BaseNode *bOpnd[2];
};



```