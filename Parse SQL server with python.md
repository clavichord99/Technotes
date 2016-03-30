#Parse SQL with Python

This is an [example link](http://example.com/).

I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].  

[1]: http://google.com/        "Google" 
[2]: http://search.yahoo.com/  "Yahoo Search" 
[3]: http://search.msn.com/    "MSN Search"

##Basic info
User pypyodbc
> pip3 install pypyodbc

##Sample code
>DatabaseString = "NJDKMonitor2"
>ConnectionString = "DRIVER={SQL Server};SERVER=192.168.1.109;UID=geomos_admin2;PWD=geomos_admin_2006;DATABASE=" +  DatabaseString
>Conn = pypyodbc.connect(ConnectionString)
> \#CustomText1 as Point Group
>SQLString = """
>             Select Result.CustomText1, Result.PointNo,Result.ProfileName, Result.Time, Result.TargetEasting, Result.TargetNorthing, Result.TargetElevation
>             From PointReportView Result
>             Where DATEDIFF(hour, Result.Time, getdate())<24
>             Order by Result.Time DESC
>           """
>Cur = Conn.cursor()
>Cur.execute(SQLString)

