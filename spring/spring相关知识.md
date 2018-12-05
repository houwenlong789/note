# exception hendler
http://www.baeldung.com/exception-handling-for-rest-with-spring

# aspectJ and spring aop

http://www.baeldung.com/aspectj

# Method Constraints with Bean Validation 2.0
http://www.baeldung.com/javax-validation-method-constraints

# life cycle

### 生命周期

1. 连接地址 https://www.concretepage.com/spring/spring-bean-life-cycle-tutorial


### BeanFactoryPostProcessor  vs  BeanPostProcessor

1. A bean implementing BeanFactoryPostProcessor is called when all bean definitions will have been loaded, but no beans will have been instantiated yet. This allows for overriding or adding properties even to eager-initializing beans. This will let you have access to all the beans that you have defined in XML or that are annotated (scanned via component-scan).
2. A bean implementing BeanPostProcessor operate on bean (or object) instances which means that when the Spring IoC container instantiates a bean instance then BeanPostProcessor interfaces do their work.
3. BeanFactoryPostProcessor implementations are "called" during startup of the Spring context after all bean definitions will have been loaded while BeanPostProcessor are "called" when the Spring IoC container instantiates a bean (i.e. during the startup for all the singleton and on demand for the proptotypes one)


### Force a bean to be the first to initialize

1. 方法1

```
         
/** 
 * An example spring pre-initializer.  Referncing this class as a bean in an  
 * application context will cause it to be the first executed PostProcessor  
 * after all beans in the application context are defined. 
 */  
public class PreInitializer implements BeanFactoryPostProcessor, PriorityOrdered {  
 @Override  
 public int getOrder() {  
  return Ordered.HIGHEST_PRECEDENCE;  
 }  
 @Override  
 public void postProcessBeanFactory(  
   ConfigurableListableBeanFactory beanFactory) throws BeansException {  
  /* put initialization code here */  
 }  
}  
```