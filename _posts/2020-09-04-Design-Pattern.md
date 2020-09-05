# 设计模式

## 设计模式六大原则

1. 单一责任原则 类或者方法责任尽量单一
2. 里氏替换原则 子类不改变父类的功能，只对其进行拓展
3. 接口隔离原则 类依赖的接口尽可能少，接口的粒度不能过打
4. 依赖倒置原则 上层不依赖下层，依赖抽象；抽象不依赖实现，实现依赖抽象
5. 迪米特原则   最少知道原则，尽量减少对其他类的依赖
6. 开闭原则     对修改封闭，对扩展开放

## 常用设计模式

1. 工厂模式：主要解决接口选择的问题。单个接口有多个实现类，我们设计一个工厂来生产这些实例对象，工厂暴露出适当的接口提供可选的类型，调用后由工厂来实例化对应的实例。
2. 抽象工厂模式：主要解决接口选择的问题。抽象工厂中包含多个工厂，相当于一类产品的实例过程，其中每种再由各自的工厂生成。
3. 单例模式：一个全局使用的类频繁地创建与销毁。保证一个类仅有一个实例，并提供一个访问它的全局访问点。
4. 建造者模式：主要解决一个类实例过程中构建比较复杂的问题。将变与不变分离开。
5. 原型模式：用原型实例指定创建对象的种类，并且通过拷贝这些原型创建新的对象。
6. 适配器模式：将一个类的接口转换成客户希望的另外一个接口。适配器模式使得原本由于接口不兼容而不能一起工作的那些类可以一起工作。适配器继承或依赖已有的对象，实现想要的目标接口。
7. 桥接模式：将抽象部分与实现部分分离，使它们都可以独立的变化。通过把部分功能抽取成单独的类，对象持有这个类的实例来实现功能，而不通过继承来实现。
8. 过滤器模式：这种模式允许开发人员使用不同的标准来过滤一组对象，通过逻辑运算以解耦的方式把它们连接起来。这种类型的设计模式属于结构型模式，它结合多个标准来获得单一标准。
9. 组合模式：它在我们树型结构的问题中，模糊了简单元素和复杂元素的概念，客户程序可以像处理简单元素一样来处理复杂元素，从而使得客户程序与复杂元素的内部结构解耦。树枝和叶子实现统一接口，树枝内部组合该接口。
10. 装饰器模式：创建了一个装饰类，用来包装原有的类，并在保持类方法签名完整性的前提下，提供了额外的功能。类似静态代理，比如ContextWrapper
11. 外观模式：为子系统中的一组接口提供一个一致的界面，外观模式定义了一个高层接口，这个接口使得这一子系统更加容易使用。在客户端和复杂系统之间再加一层，这一层将调用顺序、依赖关系等处理好。
12. 享元模式：在有大量对象时，有可能会造成内存溢出，我们把其中共同的部分抽象出来，如果有相同的业务请求，直接返回在内存中已有的对象，避免重新创建。例如retrofit2的ServiceMethodCache
13. 代理模式：在直接访问对象时带来的问题，比如说：要访问的对象在远程的机器上。在面向对象系统中，有些对象由于某些原因（比如对象创建开销很大，或者某些操作需要安全控制，或者需要进程外的访问），直接访问会给使用者或者系统结构带来很多麻烦，我们可以在访问此对象时加上一个对此对象的访问层。例如BinderProxy
14. 责任链模式：职责链上的处理者负责处理请求，客户只需要将请求发送到职责链上即可，无须关心请求的处理细节和请求的传递，所以职责链将请求的发送者和请求的处理者解耦了。例如：Android事件分发，Okhttp拦截器
15. 命令模式：将一个请求封装成一个对象，从而使您可以用不同的请求对客户进行参数化。可以认为UI上的每个控件就是个命令。
16. 迭代器模式：不同的方式来遍历整个整合对象。把在元素之间游走的责任交给迭代器，而不是聚合对象。
17. 观察者模式：一个对象状态改变给其他对象通知的问题，而且要考虑到易用和低耦合，保证高度的协作。
18. 状态模式：允许对象在内部状态发生改变时改变它的行为，对象看起来好像修改了它的类。
19. 模板模式：定义一个操作中的算法的骨架，而将一些步骤延迟到子类中。模板方法使得子类可以不改变一个算法的结构即可重定义该算法的某些特定步骤。比如继承AQS的Sync，Activity