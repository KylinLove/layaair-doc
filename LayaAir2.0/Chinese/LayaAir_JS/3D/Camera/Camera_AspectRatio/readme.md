# 摄像机的横纵比

###### **version :2.7.0beta   Update:2020-6-11**

​	我们一般不会手动设置屏幕的横纵比，在运行过程中会通过计算自动设置横纵比。但是在一些特殊的情况下需要对横纵比手动设置时，可以自己手动设置。如果需要重置横纵比，变回自动改变横纵比，只需要将这个值设置为0。

```typescript
//手动设置横纵比
camera.aspectRatio = 2;
```

```typescript
//重置
camera.aspectRatio = 0;
```

