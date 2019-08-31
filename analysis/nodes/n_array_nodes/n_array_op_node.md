


```
class NaryOpnds {
 public:
  explicit NaryOpnds(MapleAllocator *mpallocter) : nOpnd(mpallocter->Adapter()) {}

 private:
  MapleVector<BaseNode*> nOpnd;
};

```