# unityweb
Automatically exported from http://code.google.com/p/unityweb

The WWW class in Unity3D is deficient in many ways.

Unity3D WebPlayer and iOS builds cannot use System.Net.WebRequest due to security concerns. The solution? Write a HTTP class from scratch, based on plain old sockets.


# BasicUsage
This is the simplest way to use HTTP.

Simple Example
Note, the usage of Thread.Sleep is not mandatory, it just helps my unit tests play nice with MonoDevelop.

```
var r = new Request("get", "http://www.google.com/");
r.Send();
while(!r.isDone) Thread.Sleep(100);
Console.WriteLine(r.response.status);
Console.WriteLine(r.response.Text);
```
