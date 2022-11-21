~~~
import 'dart:convert' as convert;

import 'package:http/http.dart' as http;

void main() async{
  final urlUser4 = Uri.https('jsonplaceholder.typicode.com','posts/4');
  final jsonResponse = await http.get(urlUser4);
  final user = User(jsonResponse.body);
  print("El titulo es: ${user.title!}");
  print("El cuerpo es: ${user.body!}");

}

class User{
  String? title;
  String? body;

  User(String json){
  final jsonResponse = convert.jsonDecode(json);
  title = jsonResponse["data"]["title"];
  body = jsonResponse["data"]["body"];
 }
}
~~~
