#### 防抖函数
  当持续触发事件时，一定时间段内没有再触发事件，事件处理函数才会执行一次，如果设定的时间到来之前，又一次触发了事件，就重新开始 延时

#### 代码实现

    function debounce(fn, timeout) {
      let timer;

      return function() {
        clearTimeout(timer);
        timer = setTimeout(fn, timeout);
      }
    }

关于延迟时间的处理，此处涉及到了[闭包](closure.md)的知识。