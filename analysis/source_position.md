to store source position information

```

// 
class SrcPosition {
 public:
  SrcPosition() : lineNum(0), mplLineNum(0) {
    u.word0 = 0;
  }

  virtual ~SrcPosition() = default;

  uint32 RawData() const {
    return u.word0;
  }

  uint32 FileNum() const {
    return u.fileColumn.fileNum;
  }

  uint32 Column() const {
    return u.fileColumn.column;
  }

  uint32 LineNum() const {
    return lineNum;
  }

  uint32 MplLineNum() const {
    return mplLineNum;
  }

  void SetFileNum(uint16 n) {
    u.fileColumn.fileNum = n;
  }

  void SetColumn(uint16 n) {
    u.fileColumn.column = n;
  }

  void SetLineNum(uint32 n) {
    lineNum = n;
  }

  void SetRawData(uint32 n) {
    u.word0 = n;
  }

  void SetMplLineNum(uint32 n) {
    mplLineNum = n;
  }

  void CondSetLineNum(uint32 n) {
    lineNum = lineNum ? lineNum : n;
  }

  void CondSetFileNum(uint16 n) {
    uint16 i = u.fileColumn.fileNum;
    u.fileColumn.fileNum = i ? i : n;
  }

 private:
  union {
    struct {
      uint16 fileNum;
      uint16 column;
      bool stmtBegin;
      bool bbBegin;
      uint16 unused;
    } fileColumn;

    uint32 word0;
  } u;

  uint32 lineNum;     // line number of original src file, like foo.java
  uint32 mplLineNum;  // line number of mpl file
};

```