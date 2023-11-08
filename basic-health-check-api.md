#### 1. Create Spring boot app using spring initializer
#### 2. Create a **Health Controller File**

```kotlin
import org.springframework.web.bind.annotation.GetMapping
import org.springframework.web.bind.annotation.RequestMapping
import org.springframework.web.bind.annotation.RestController

@RestController
@RequestMapping("api/health")
class HealthController {

    @GetMapping("")
    fun getHealth():String{
        return "API is running fine"
    }
}
```

#### 3. Open postman
#### 4. Hit ```http://localhost:8080/api/health``` to check the output
