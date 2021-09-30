## 面试题

## 一面 微信通话

- http://sourse.kahoul.top/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20210926175914.jpg

```js
hello bigo
```

- http://sourse.kahoul.top/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20210926175906.jpg
- http://sourse.kahoul.top/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20210926175909.jpg

```js
1224
```

- http://sourse.kahoul.top/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20210926175842.png

```js
var prevConsoleLog = console.log

console.log = function () {
  prevConsoleLog(new Date().getTime())
  prevConsoleLog(...arguments)
}

console.log('test')
```

- http://sourse.kahoul.top/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20210926175850.png

```js
var isBigVersio = (curVer, tarVer) => {
  let curList = curVer.split('.')
  let tarList = tarVer.split('.')
  while (curList.length && tarList.length) {
    let curNum = Number(curList.shift())
    let tarNum = Number(tarList.shift())
    if (tarNum > curNum) {
      return false
    } else if (tarNum < curNum) {
      return true
    }
  } //走到这里来还不return  表明前缀是一样的     1.1.2   1.1
  return !!curList.length
}

console.log(isBigVersio('1.1.0', '1.2.1'))
```

- http://sourse.kahoul.top/%E5%BE%AE%E4%BF%A1%E5%9B%BE%E7%89%87_20210926175857.png

- https://leetcode-cn.com/problems/number-of-digit-one/solution/shu-zi-1-de-ge-shu-by-leetcode-solution-zopq/

```js
const findOneNum = arr => {
  let res = 0
  for (var i = 0; i < arr.length; i++) {
    let itemSum = { current: 0 }
    findOneNumByTargetNum(arr[i], itemSum)
    res += itemSum.current
  }
  return res
}

function findOneNumByTargetNum(num, sum = 0) {
  let ret = num % 10 // 取余出个位数
  let prevRet = Math.floor(num / 10) // console.log('findOneNumByTargetNum', 'num', num, 'sum', sum, 'prevRet', prevRet)
  if (prevRet > 0) {
    findOneNumByTargetNum(prevRet, sum)
  }

  if (ret === 1) {
    // console.log('num', num)
    sum.current++ // return 1
  } // return sum
}
console.log(findOneNum([1, 10, 11, 12, 13]))
```

- http 和 https 区别
- https 如何加密解密
- 浏览器缓存

## 二面 微信视频通话
- react class和function component的生命周期类比
- 用react有做过什么优化
- 项目有做过什么优化
- 在豌豆加班多吗

```js
const diffJson = (obj1, obj2) => {
  let flag = false

  let res = hackDiffJson(obj1, obj2)
  let res2 = hackDiffJson(obj2, obj1)

  function hackDiffJson(param1, params2) {
    let hackFlag = true
    Object.keys(param1).forEach(key => {
      let param1Val = param1[key]
      let params2Val = params2[key]
      if (!params2Val || params2Val !== param1Val) {
        hackFlag = false
      }
    })

    return hackFlag
  }

  flag = res && res2
  return flag
}

// 少了递归处理，做得不对，网上很多答案了
console.log(diffJson({ name: 'taobao', age: 18 }, { name: 'taobao', age: 18 }))

console.log(diffJson({ name: 'alibaba', age: 20 }, { name: 'taobao', age: 18 }))
```

## 面试感想

BIGO live 直播 项目 app 内嵌 技术团队 项目组前端 10 人左右 技术栈 vue2 + ts  二面挂
