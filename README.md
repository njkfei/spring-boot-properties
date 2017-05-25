# spring-boot-properties
抄自mkyong

## 坑
 * 加载yaml配置文件的方法
 * Created by sun on 2017-1-15.
 * spring-boot更新到1.5.2版本后locations属性无法使用
 * @PropertySource注解只可以加载proprties文件,无法加载yaml文件
 * 故现在把数据放到application.yml文件中,spring-boot启动时会加载
 
 demo:
 ```
 @Component
@ConfigurationProperties(locations = {"classpath:test.yml"},prefix = "test")
//@PropertySource("classpath:test.yml")
@Data
public class TestConfig {

    private String key;
    private String secretKey;
    
    @PostConstruct
    private void init(){
        System.out.println(key);
        System.out.println(secretKey);
    }

}
 ```

## keng 2
yml文件，不要使用中文
