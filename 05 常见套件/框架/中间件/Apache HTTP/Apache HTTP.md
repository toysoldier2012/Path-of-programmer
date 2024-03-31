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

``` java
import org.apache.http.HttpEntity;
import org.apache.http.client.HttpClient;
import org.apache.http.client.methods.HttpPost;
import org.apache.http.entity.ContentType;
import org.apache.http.entity.mime.MultipartEntityBuilder;
import org.apache.http.impl.client.HttpClients;

import java.io.File;

HttpClient client = HttpClients.createDefault();
HttpPost post = new HttpPost("http://example.com/upload");

// 构建Multipart请求体
MultipartEntityBuilder builder = MultipartEntityBuilder.create();

// 添加一个名为'mail'的JSON对象，这里假设你已经有了JSON字符串
// 例如：String jsonMail = "{\"subject\":\"Test\", \"body\":\"This is a test\"}";
// ContentType.APPLICATION_JSON表示这部分内容是JSON格式
builder.addTextBody("mail", jsonMail, ContentType.APPLICATION_JSON);

// 添加文件，假设文件路径已经保存在某个列表或数组中
// 例如：List<String> filePaths = Arrays.asList("path/to/file1.pdf", "path/to/file2.docx");
for (String filePath : filePaths) {
    File file = new File(filePath);
    ContentType contentType = ContentType.DEFAULT_BINARY;
    
    // 根据文件扩展名设置内容类型
    if (filePath.endsWith(".pdf")) {
        contentType = ContentType.create("application/pdf");
    } else if (filePath.endsWith(".docx")) {
        contentType = ContentType.create("application/vnd.openxmlformats-officedocument.wordprocessingml.document");
    }
    
    builder.addBinaryBody("files", file, contentType, file.getName());
}

// 构建并设置请求体
HttpEntity multipart = builder.build();
post.setEntity(multipart);

// 发送请求
HttpResponse response = client.execute(post);

// 处理响应
```

Apache HttpClient库中，包含多个静态类，用于生成header

如`org.apache.http.HttpHeaders`

- `HttpHeaders.AUTHENTICATION`
- `HttpHeaders.CONTENT_TYPE`
- `HttpHeaders.CACHE_CONTROL`
- `HttpHeaders.USER_AGENT`
- `HttpHeaders.ACCEPT`

对于MIME类型的处理，这个类位于`org.apache.http.entity.ContentType`中

- `APPLICATION_ATOM_XML`：`"application/atom+xml"`
- `APPLICATION_FORM_URLENCODED`：`"application/x-www-form-urlencoded"`
- `APPLICATION_JSON`：`"application/json"`
- `APPLICATION_OCTET_STREAM`：`"application/octet-stream"`
- `APPLICATION_SVG_XML`：`"application/svg+xml"`
- `APPLICATION_XHTML_XML`：`"application/xhtml+xml"`
- `APPLICATION_XML`：`"application/xml"`
- `MULTIPART_FORM_DATA`：`"multipart/form-data"`
- `TEXT_HTML`：`"text/html"`
- `TEXT_PLAIN`：`"text/plain"`
- `TEXT_XML`：`"text/xml"`
- `WILDCARD`：`"*/*"`

