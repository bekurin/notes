
```
@Retention(AnnotationRetention.RUNTIME) @Target(AnnotationTarget.PARAMETER) annotation class CustomRequestParam(val separator: String = ",")

class CustomStringToListConverter(private val separator: String) : Converter<String, List<String>> { override fun convert(source: String): List<String> { return source.split(separator) } }

@EnableWebMvc class ApplicationConfig : WebMvcConfigurerAdapter() { override fun addArgumentResolvers(registry: ConfigurableArgumentResolverRegistry) { registry.addCustomArgumentResolver(RequestParamArgumentResolver(null, CustomStringToListConverter("|"))) } }
```