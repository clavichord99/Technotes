**Parse SQL with Python***

#Basic info
User pypyodbc
> pip3 install pypyodbc

# Sample code
>DatabaseString = "NJDKMonitor2"
>ConnectionString = "DRIVER={SQL Server};SERVER=192.168.1.109;UID=geomos_admin2;PWD=geomos_admin_2006;DATABASE=" +  DatabaseString
>Conn = pypyodbc.connect(ConnectionString)
>#CustomText1 as Point Group
>SQLString = """
>             Select Result.CustomText1, Result.PointNo,Result.ProfileName, Result.Time, Result.TargetEasting, Result.TargetNorthing, Result.TargetElevation
>             From PointReportView Result
>             Where DATEDIFF(hour, Result.Time, getdate())<24
>             Order by Result.Time DESC
>           """
>Cur = Conn.cursor()
>Cur.execute(SQLString)

