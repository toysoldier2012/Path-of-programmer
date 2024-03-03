#apache #http

# Hello world

```Java
import org.apache.http.HttpResponse;
import org.apache.http.NameValuePair;
import org.apache.http.client.HttpClient;
import org.apache.http.client.entity.UrlEncodedFormEntity;
import org.apache.http.client.methods.HttpPost;
import org.apache.http.impl.client.HttpClients;
import org.apache.http.message.BasicNameValuePair;
import java.util.ArrayList;
import java.util.List;

public class HttpPostExample {
    public static void main(String[] args) {
        try {
            // 创建HttpClient实例
            HttpClient client = HttpClients.createDefault();
            
            // 创建HttpPost实例
            HttpPost post = new HttpPost("http://www.example.com/api/resource"); 
            
            // 添加表单参数
            List<NameValuePair> urlParameters = new ArrayList<>();
            urlParameters.add(new BasicNameValuePair("param1", "value1"));
            urlParameters.add(new BasicNameValuePair("param2", "value2"));
            post.setEntity(new UrlEncodedFormEntity(urlParameters));
            
            // 发送POST请求
            HttpResponse response = client.execute(post);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

Pour envoyer une requête [[HTTP]], on doit préparer les parties suivantes:

- [[HttpClient]]

## POST

- [[HttpPost]]
- [[HttpEntity]]
