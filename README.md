# go_learning
go_learning

1. rpc 调用 client传输的res为二重指针
  type T struct {
    a int
  }
  res = &T{}
  err := client.Call(_func, arg, &res)
  
  // server接收
  func(c context.Context, a *Arg, res **T) (err error)
  //此时，*res为nil
