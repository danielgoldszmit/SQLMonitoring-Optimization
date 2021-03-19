## START FROM THE OUTSIDE IN

- Environment
    
- VM - Disk Size, Storage Size
    
- Azure Monitor
    
- Dynamic Management Views (DMV's) and Wait Stats
    
- Query Store
    
- Extended Events (XEvents)
    
    > ![Layered Approach](https://github.com/danielgoldszmit/SQLMonitoring-Optimization/blob/main/Assets/SQLOptimizationLayeredApproach.PNG)
    

1. Look over performance guidelines for the SQL VM and going through the check list
    
    - [https://docs.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/performance-guidelines-best-practices](https://docs.microsoft.com/en-us/azure/azure-sql/virtual-machines/windows/performance-guidelines-best-practices)
2. Enable the Query Store if you are running SQL VM (Query Store is enabled by default in Azure SQL DB)
    
    - [Monitoring performance by using the Query Store](https://docs.microsoft.com/en-us/sql/relational-databases/performance/monitoring-performance-by-using-the-query-store?view=sql-server-ver15)
        
    - [Query Performance Insight for Azure SQL Database](https://docs.microsoft.com/en-us/azure/azure-sql/database/query-performance-insight-use)
        
    - [Best practices with Query Store](https://docs.microsoft.com/en-us/sql/relational-databases/performance/best-practice-with-the-query-store?view=sql-server-ver15)
        

3. Leveraging the Performance Dashboard if you are running SQL VM or SQL Managed Instance
    
    - [https://docs.microsoft.com/en-us/sql/relational-databases/performance/performance-dashboard?view=sql-server-ver15](https://docs.microsoft.com/en-us/sql/relational-databases/performance/performance-dashboard?view=sql-server-ver15)
4. Using Log Analytics
    
    - ![SQL Assessment Solution](https://github.com/danielgoldszmit/SQLMonitoring-Optimization/blob/main/Assets/sqlassessment.png) SQL Assessment Solution for SQL VMs (SQL Health Check) - [https://docs.microsoft.com/en-us/azure/azure-monitor/insights/sql-assessment](https://docs.microsoft.com/en-us/azure/azure-monitor/insights/sql-assessment)
        
        - The sql assessement solution supports SQL Server version 2012, 2014, 2016, 2017, and 2019.
    - ![SQL Assessment Solution](https://github.com/danielgoldszmit/SQLMonitoring-Optimization/blob/main/Assets/azuresqllanalyitcs.png) Azure SQL Analytics Solution for Azure SQL DBs and Managed Instance - [https://docs.microsoft.com/en-us/azure/azure-monitor/insights/azure-sql](https://docs.microsoft.com/en-us/azure/azure-monitor/insights/sql-assessment)
        
        - The sql assessement solution supports SQL Server version 2012, 2014, 2016, 2017, and 2019.
5. Verify Deployment
    
    - What Version are you running
    - What Engine Edition
    - What is the DB name, creation date, compatibility level, collation
    - Verify server memory configuration options
    - Gets back DTU limits, CPU limits, Memory limits, Size limits, Log limits
    - Verify installed physical memory, memory usage, memory model, service startup time
    - [Verify Deployment.md](https://github.com/danielgoldszmit/SQLMonitoring-Optimization/blob/main/1.VerifyDeployment.md)
6. Azure SQL Database Tips (If you're running Azure SQL DB)
    
    - [Improving your databases with Azure SQL Database tips](https://techcommunity.microsoft.com/t5/azure-sql/improving-your-databases-with-azure-sql-database-tips/ba-p/2094678) 
    - [Azure SQL Tips](https://github.com/microsoft/azure-sql-tips)
    - [Azure SQL Tips Notebook.ipynb](https://github.com/danielgoldszmit/SQLMonitoring-Optimization/blob/main/2.AzureSQLDBTips.ipynb)
7. Run Wait Stats (Good for SQL VM, MI and Azure SQL DBs)
    
    - [SQL Server Wait Statistics (or please tell me where it hurts…)](https://www.sqlskills.com/blogs/paul/wait-statistics-or-please-tell-me-where-it-hurts/)
    - [Get Wait Stats.ipynb](.\3.GetWaitStats.ipynb)
8. Monitor Performance with DMVs
    
    - [SQL Performance DMVs.ipynb](.\4.SQLPerformanceDMVs.ipynb)
9. Monitor and Optimize Indexes
    
    - [Index Optimization.ipynb](.\5.IndexOptimization.ipynb)
10. What bucket does your issue fall into? 

- Issue is either running alot or waiting alot
- Running alot - You have a CPU issue and your queries are running hot or you have a query compilation problem
- Waiting alot - You have Blocking isses, IO issues because of a lack of indexes, or you have a tempdb contention.

 > ![Layered Approach](https://github.com/danielgoldszmit/SQLMonitoring-Optimization/blob/main/Assets/buckets.png)
