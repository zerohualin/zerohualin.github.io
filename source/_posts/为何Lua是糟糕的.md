- 难重构

```lua
  local hero = mHeroManager.GetHero()
  print(hero.ship.go)
	--删除一个属性后，很可能在系统的某个角落漏掉。
```

- 难阅读

- 复杂需求下无力

  ![蓝大谈论](Image/蓝大讨论Lua不是强类型.jpg)

