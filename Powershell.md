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
<br>

[出力を整える](https://www.vwnet.jp/windows/PowerShell/2018060501/GettingStartedWithPowerShell-03.htm)  
- Format-Table(ft)  指定したプロパティをテーブル表示  
```
PS C:\Users\airt002> Get-ChildItem C:\Windows\System32\drivers\etc\ | Format-Table FullName, LastWriteTime, Length -AutoSize

FullName                                    LastWriteTime         Length
--------                                    -------------         ------
C:\Windows\System32\drivers\etc\hosts       8/8/2022 11:53:08 AM    1056
C:\Windows\System32\drivers\etc\hosts.ics   1/16/2023 11:50:20 AM    443
C:\Windows\System32\drivers\etc\lmhosts.sam 12/7/2019 6:12:44 PM    3683
C:\Windows\System32\drivers\etc\networks    7/10/2015 8:02:42 PM     407
```
<br>

-  Format-List(fl)  指定したプロパティをリスト表示  
```
PS C:\Users\airt002> Get-ChildItem C:\Windows\System32\drivers\etc\ | Format-List FullName, LastWriteTime, Length


FullName      : C:\Windows\System32\drivers\etc\hosts
LastWriteTime : 8/8/2022 11:53:08 AM
Length        : 1056

FullName      : C:\Windows\System32\drivers\etc\hosts.ics
LastWriteTime : 1/16/2023 11:50:20 AM
Length        : 443
```
<br>

- 




