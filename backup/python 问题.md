## 手动设置一个矩形的外围轮廓
```
init=[]
x = np.linspace(0, 4000, 4000)
y = np.linspace(0, 3096, 4000)
zero=np.zeros(4000)
ymax=zero+3096
xmax=zero+4000
init.append(np.array([zero, y]).T) 
init.append(np.array([x, zero]).T)
init.append(np.array([x, ymax]).T)
init.append(np.array([xmax, y]).T)
init= np.vstack(init)
snake = active_contour(image_smooth, init, alpha=0.01, beta=10, gamma=0.001)
```