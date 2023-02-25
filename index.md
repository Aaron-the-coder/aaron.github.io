---
title: Welcome to my blog
---
# MockK
## Basic Syntax
- every: get a certain result for every operation
- eq: equal, can be omit because a number itself can mean equal. eg: every { mock.call(more(5), 6) } returns 1
// is same as
every { mock.call(more(5), eq(6)) } returns 1
- returnsMany: return a number of result. eg: ```every { mock1.call(5) } returnsMany listOf(1, 2, 3)```
- andThen: indicate the following operations. eg: ```every { mock1.call(5) } returns 1 andThen 2 andThen 3```
- just Runs: use it when the return value is null. eg: ```every { mock1.callReturningUnit(5) } just Runs```
- When the return value is a lamda expretion, use "answers". eg: ``` every { mock1.call(5) } answers { arg<Int>(0) + 5 }```
- Verify: to verify the a method's called times. We can add parameters to this keyword(adLeast:the minimum times the method should be called; atMost: the maximum times the method can be called; exactly: the exact times the method should be called.
- wasNot called: this parameter can be added to the end of the method name in a "verify" block to verify a method is not called.
  - verifySequence: verify the excact sequence happened. eg:
  ``` 
  verifySequence {
  mock1.call(1)
  mock1.call(2)
  mock1.call(3)
  } 
  ```
