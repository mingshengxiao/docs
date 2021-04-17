##### 节流函数
  在一定时间内，不管事件被触发了多少次，当时间结束时，事件只会执行一次

##### 代码实现

    // 时间戳
    function throttle(fn, threshHold) {
      let last;

      return function() {
        const now = new Date();
        if (last && now - last >= thresHold) {
          last = now;
          fn.apply(this,arguments);
        }
      }
    }