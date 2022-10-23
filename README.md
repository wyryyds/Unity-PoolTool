# HAIPoolTool
A general object pool plugin for personal development for your Unity project
## How to use it for your project？
You just need to clone it to any folder of yours and choose to import it in the Import Package in the unity panel.  
You need to create an empty object named PoolManager in your project, it will act as your object pool manager, after that you should add the script "PoolManager" to it, you can find it in the getcomponent panel, or in in your scripts folder.
## Its function
This is a general object pool plugin that allows you to generate object pools for multiple items through configuration or code for unified management.
### Initialize the object pool
You can initialize your object pool by drag and drop in unity's hierarchy panel, like this
![image](https://github.com/wyryyds/HAIPoolTool/blob/main/ImageFloder/01.png)   
Of course, you can also create object pools in code.Just call the method
```
PoolManager.Instance.AddToPool(string tag,GameObject poolItemObj,int Count)
```
### Take and Recycle
You can take a single game object by the pool name, or you can take any number of objects by yourself, and call the following method：
```
PoolManager.Instance.GetPoolObject(string tag)
PoolManager.Instance.GetPoolObjects(string tag,int count)
```
Likewise, we support you to recycle a single game object or multiple：
```
PoolManager.Instance.RecycleObjectToPool(string tag,GameObject poolObj)
PoolManager.Instance.RecycleObjectsToPool(string tag)
```
### Automatic expansion
You don't need to worry about its usage. When the pool exists and is exhausted, it will adopt an exponential growth strategy of 2 to expand one of your object pools.
### Clearing the object pool
You can choose to destroy a single object pool by character index, or you can call a method to destroy all object pools：
```
PoolManager.Instance.ClearAnyPool(string tag)
PoolManager.Instance.ClearAllPool()
```
## Advantages and disadvantages
It can be very convenient for you to create object pools for any object in the form of different names, and manage nodes at the same time, and the efficiency of taking and recycling is very good. Of course, I am not providing more interfaces to facilitate your other ideas and operations. I choose to leave it to you to implement more details. In addition, you can also use direct inheritance to customize the object pool that better suits your needs, which I believe would be a great thing.
