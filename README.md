QuickJson
---------
Java 操作json框架

代码示例

```Java
public class QuickJsonTest {

	@Test
	public void test1() {
		JSONObject jsonObject = (JSONObject) JSON.parse("{\"array\":[1,2,3],\"boolean\":true,\"null\":null,\"number\":123,\"object\":{\"a\":\"b\",\"c\":\"d\",\"e\":\"f\"},\"string\":\"Hello World\"}");
		System.out.println(jsonObject.getStringValue("string"));
		System.out.println(jsonObject.getJSONObject("string"));
	}
	
	@Test
	public void test2() {
		System.out.println(JSON.parse("{\"name\":\"Tom\",\"age\":10,\"address\":\"anhui hfei\"}", A.class));
		System.out.println(JSON.parseJSONObject("{\"name\":\"Tom\",\"age\":10,\"address\":\"anhui hfei\"}").toPojo(A.class));
		System.out.println(JSON.parseJSONArray("[{\"name\":\"Tom\",\"age\":10,\"address\":\"anhui hfei\"}]").getPojoValue(0, A.class));
	}
	
	@Test
	public void test3() {
		System.out.println(JSON.toJSONString(new A("Tom", 11, "anhui hefei")));
		System.out.println(JSON.toJSONString(new int[]{10,10,102,200}));
		HashMap<String, Object> map = new HashMap<String,Object>();
		map.put("name", "Tom");
		map.put("age",11);
		map.put("address", "anhui hefei");
		System.out.println(JSON.toJSONString(map));
		List<String> list = new ArrayList<String>();
		list.add("Tom");
		list.add("jack");
		System.out.println(JSON.toJSONString(list));
	}
}

```
运行结果
```
Hello World
null
A [name=Tom, age=10, address=anhui hfei]
A [name=Tom, age=10, address=anhui hfei]
A [name=Tom, age=10, address=anhui hfei]
{"address":"anhui hefei","name":"Tom","age":11}
[10,10,102,200]
{"address":"anhui hefei","age":11,"name":"Tom"}
["Tom","jack"]

```