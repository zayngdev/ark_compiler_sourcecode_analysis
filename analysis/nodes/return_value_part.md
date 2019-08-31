class ReturnValuePart {
 public:
  explicit ReturnValuePart(MapleAllocator *allocator) : returnValues(allocator->Adapter()) {}

  virtual ~ReturnValuePart() = default;

 private:
  CallReturnVector returnValues;
};