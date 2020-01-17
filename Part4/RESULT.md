
##What does the code do?
At a first clance,the incrementing function  counts to a 1000000 and the decrementing function should count down from 1000000. However the problem araises when we call these two threads at the same time. The threads then are working in overlapping time periods which distort the number. This is an example of when concurrency doesn't work as intended. 