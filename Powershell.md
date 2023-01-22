# Powershell

[PowerShell で行数や文字数をカウントする](https://operationslab.wordpress.com/2013/03/12/powershell-%E3%81%A7%E8%A1%8C%E6%95%B0%E3%82%84%E6%96%87%E5%AD%97%E6%95%B0%E3%82%92%E3%82%AB%E3%82%A6%E3%83%B3%E3%83%88%E3%81%99%E3%82%8B/)<br>
PowerShell では以下の方法で行数や文字数をカウントする事が出来ます。
- [Measure-Object](http://technet.microsoft.com/ja-jp/library/hh849965.aspx) コマンドレットを使用する
- Count プロパティ又は Length プロパティを使用する
<br>
```
PS C:\Users\Administrator> $log = Get-Content C:\Windows\WindowsUpdate.log
PS C:\Users\Administrator> $log | Measure-Object -Line -Character -Word | Format-List Lines,Words,Characters
Lines      : 10548
Words      : 123639
Characters : 1132103
```
```
PS C:\Users\Administrator> $log.GetType()
IsPublic IsSerial Name     BaseType
-------- -------- ----     --------
True     True     Object[] System.Array
 
PS C:\Users\Administrator> $log | Measure-Object | Format-List Count
Count : 10548
```
```
PS C:\Users\Administrator> $log.Count
10548
 
PS C:\Users\Administrator> $log.Length
10548
```



