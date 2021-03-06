<h1 align="center"> 🦄 FreeSql </h1><div align="center">

FreeSql is a powerful O/RM component, supports .NET Core 2.1+, .NET Framework 4.0+, and Xamarin.

[![Member project of .NET Core Community](https://img.shields.io/badge/member%20project%20of-NCC-9e20c9.svg)](https://github.com/dotnetcore) 
[![nuget](https://img.shields.io/nuget/v/FreeSql.svg?style=flat-square)](https://www.nuget.org/packages/FreeSql) 
[![stats](https://img.shields.io/nuget/dt/FreeSql.svg?style=flat-square)](https://www.nuget.org/stats/packages/FreeSql?groupby=Version) 
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/2881099/FreeSql/master/LICENSE.txt)

<p>
    <span>English</span> |  
    <a href="README.zh-CN.md">中文</a>
</p>

</div>

- 🛠 Support CodeFirst mode, support data migration even when using Access database.
- 💻 Support DbFirst mode, support import entity class from database, or use [Entity Class Generation Tool](https://github.com/2881099/FreeSql/wiki/DbFirst) to generate entity class.
- ⛳ Support advanced type mapping, such as PostgreSQL array type, etc.
- ✒ Support large number of expression functions, and highly customizable analysis.
- 🏁 Support one-to-many and many-to-many greedy loading of navigation properties, and lazy loading.
- 📃 Support Read/Write separation, Splitting Table/Database, Filters, Optimistic Locking and pessimistic locking.
- 🌳 Support MySql/SqlServer/PostgreSQL/Oracle/Sqlite/Firebird/达梦/人大金仓/神舟通用/翰高/Access, etc.

QQ Groups：4336577(full)、**8578575(available)**、**52508226(available)**

## 📚 Documentation

| | |
| - | - |
| <img src="https://github.com/dotnetcore/FreeSql/raw/master/Examples/restful/001.png" width="30" height="46"/> |&nbsp;&nbsp;[Introduction](https://www.cnblogs.com/FreeSql/p/11531300.html)&nbsp;&nbsp;\|&nbsp;&nbsp;[Select](https://github.com/2881099/FreeSql/wiki/%e6%9f%a5%e8%af%a2)&nbsp;&nbsp;\|&nbsp;&nbsp;[Update](https://github.com/2881099/FreeSql/wiki/%e4%bf%ae%e6%94%b9)&nbsp;&nbsp;\|&nbsp;&nbsp;[Insert](https://github.com/2881099/FreeSql/wiki/%e6%b7%bb%e5%8a%a0)&nbsp;&nbsp;\|&nbsp;&nbsp;[Delete](https://github.com/2881099/FreeSql/wiki/%e5%88%a0%e9%99%a4)&nbsp;&nbsp;|
| <img src="https://github.com/dotnetcore/FreeSql/raw/master/Examples/restful/002.png" width="30" height="46"/> |&nbsp;&nbsp;[Expression Functions](https://github.com/2881099/FreeSql/wiki/%e8%a1%a8%e8%be%be%e5%bc%8f%e5%87%bd%e6%95%b0)&nbsp;&nbsp;\|&nbsp;&nbsp;[CodeFirst](https://github.com/2881099/FreeSql/wiki/CodeFirst)&nbsp;&nbsp;\|&nbsp;&nbsp;[DbFirst](https://github.com/2881099/FreeSql/wiki/DbFirst)&nbsp;&nbsp;\|&nbsp;&nbsp;[Filters](https://github.com/2881099/FreeSql/wiki/%e8%bf%87%e6%bb%a4%e5%99%a8)&nbsp;&nbsp;|
| <img src="https://github.com/dotnetcore/FreeSql/raw/master/Examples/restful/003.png" width="30" height="46"/> |&nbsp;&nbsp;[Repository](https://github.com/2881099/FreeSql/wiki/Repository)&nbsp;&nbsp;\|&nbsp;&nbsp;[UnitOfWork](https://github.com/2881099/FreeSql/wiki/%e5%b7%a5%e4%bd%9c%e5%8d%95%e5%85%83)&nbsp;&nbsp;\|&nbsp;&nbsp;[AOP](https://github.com/2881099/FreeSql/wiki/AOP)&nbsp;&nbsp;\|&nbsp;&nbsp;[DbContext](https://github.com/2881099/FreeSql/wiki/DbContext)&nbsp;&nbsp;|
| <img src="https://github.com/dotnetcore/FreeSql/raw/master/Examples/restful/004.png" width="30" height="46"/> |&nbsp;&nbsp;[Read/Write Separation](https://github.com/2881099/FreeSql/wiki/%e8%af%bb%e5%86%99%e5%88%86%e7%a6%bb)&nbsp;&nbsp;\|&nbsp;&nbsp;[Splitting Table/Database](https://github.com/2881099/FreeSql/wiki/%e5%88%86%e8%a1%a8%e5%88%86%e5%ba%93)&nbsp;&nbsp;\|&nbsp;&nbsp;[Mysterious Technology](https://github.com/2881099/FreeSql/wiki/%E9%AA%9A%E6%93%8D%E4%BD%9C)&nbsp;&nbsp;\|&nbsp;&nbsp;[FAQ](https://github.com/dotnetcore/FreeSql/wiki/%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98)&nbsp;&nbsp;\|&nbsp;&nbsp;[*Update Notes*](https://github.com/2881099/FreeSql/wiki/%e6%9b%b4%e6%96%b0%e6%97%a5%e5%bf%97)&nbsp;&nbsp;|

> FreeSql provides a variety of usage habits, and there is always one that suits you:

- Use FreeSql, keep the original usage.
- Use [FreeSql.Repository](https://github.com/2881099/FreeSql/wiki/Repository), for those who are accustomed to storage models and work units.
- Use [FreeSql.DbContext](https://github.com/2881099/FreeSql/wiki/DbContext), a bit like how efcore is used.
- Or use [FreeSql.BaseEntity](https://github.com/2881099/FreeSql/tree/master/Examples/base_entity), which is extremely simple.

> Some open source projects that use FreeSql:

- [Zhontai.net Admin, Management System](https://github.com/zhontai/Admin.Core)
- [A simple and practical CMS implemented by .NET Core](https://github.com/luoyunchong/lin-cms-dotnetcore)
- [iusaas.com SaaS, Enterprise Application Management System](https://github.com/alonsoalon/TenantSite.Server)
- [EasyCms, CMS management system used by enterprises and institutions](https://github.com/jasonyush/EasyCMS)
- [Content management system](https://github.com/hejiyong/fscms)

<p align="center">
  <img src="https://github.com/dotnetcore/FreeSql/raw/master/functions11.png"/>
</p>

## 🚀 Quick start

> dotnet add package FreeSql.Provider.Sqlite

```csharp
static IFreeSql fsql = new FreeSql.FreeSqlBuilder()
  .UseConnectionString(FreeSql.DataType.Sqlite, @"Data Source=document.db")
  .UseAutoSyncStructure(true) //automatically synchronize the entity structure to the database
  .Build(); //be sure to define as singleton mode

class Song {
  [Column(IsIdentity = true)]
  public int Id { get; set; }
  public string Title { get; set; }
  public string Url { get; set; }
  public DateTime CreateTime { get; set; }
  
  public ICollection<Tag> Tags { get; set; }
}
class Song_tag {
  public int Song_id { get; set; }
  public Song Song { get; set; }
  
  public int Tag_id { get; set; }
  public Tag Tag { get; set; }
}
class Tag {
  [Column(IsIdentity = true)]
  public int Id { get; set; }
  public string Name { get; set; }
  
  public int? Parent_id { get; set; }
  public Tag Parent { get; set; }
  
  public ICollection<Song> Songs { get; set; }
  public ICollection<Tag> Tags { get; set; }
}
```

### 🔎 Query
```csharp
//OneToOne、ManyToOne
fsql.Select<Tag>().Where(a => a.Parent.Parent.Name == "English").ToList();

//OneToMany
fsql.Select<Tag>().IncludeMany(a => a.Tags, then => then.Where(sub => sub.Name == "foo")).ToList();

//ManyToMany
fsql.Select<Song>()
  .IncludeMany(a => a.Tags, then => then.Where(sub => sub.Name == "foo"))
  .Where(s => s.Tags.AsSelect().Any(t => t.Name == "Chinese"))
  .ToList();

//Other
fsql.Select<YourType>()
  .Where(a => a.IsDelete == 0)
  .WhereIf(keyword != null, a => a.UserName.Contains(keyword))
  .WhereIf(role_id > 0, a => a.RoleId == role_id)
  .Where(a => a.Nodes.AsSelect().Any(t => t.Parent.Id == t.UserId))
  .Count(out var total)
  .Page(page, size)
  .OrderByDescending(a => a.Id)
  .ToList()
```
[More..](https://github.com/2881099/FreeSql/wiki/%e6%9f%a5%e8%af%a2)

```csharp
fsql.Select<Song>().Where(a => new[] { 1, 2, 3 }.Contains(a.Id)).ToList();

fsql.Select<Song>().Where(a => a.CreateTime.Date == DateTime.Today).ToList();

fsql.Select<Song>().OrderBy(a => Guid.NewGuid()).Limit(10).ToList();
```
[More..](https://github.com/2881099/FreeSql/wiki/%e8%a1%a8%e8%be%be%e5%bc%8f%e5%87%bd%e6%95%b0) 

### 🚁 Repository

> dotnet add package FreeSql.Repository

```csharp
[Transactional]
public void Add() {
  var repo = ioc.GetService<BaseRepository<Tag>>();
  repo.DbContextOptions.EnableAddOrUpdateNavigateList = true;

  var item = new Tag {
    Name = "testaddsublist",
    Tags = new[] {
      new Tag { Name = "sub1" },
      new Tag { Name = "sub2" }
    }
  };
  repo.Insert(item);
}
```

Reference: [Use `TransactionalAttribute` and `UnitOfWorkManager` in ASP.NET Core to Achieve the *Multiple Transaction Propagation*](https://github.com/dotnetcore/FreeSql/issues/289).

## 💪 Performance

FreeSql Query & Dapper Query

```shell
Elapsed: 00:00:00.6733199; Query Entity Counts: 131072; ORM: Dapper

Elapsed: 00:00:00.4554230; Query Tuple Counts: 131072; ORM: Dapper

Elapsed: 00:00:00.6846146; Query Dynamic Counts: 131072; ORM: Dapper

Elapsed: 00:00:00.6818111; Query Entity Counts: 131072; ORM: FreeSql*

Elapsed: 00:00:00.6060042; Query Tuple Counts: 131072; ORM: FreeSql*

Elapsed: 00:00:00.4211323; Query ToList<Tuple> Counts: 131072; ORM: FreeSql*

Elapsed: 00:00:01.0236285; Query Dynamic Counts: 131072; ORM: FreeSql*
```

FreeSql ToList & Dapper Query

```shell
Elapsed: 00:00:00.6707125; ToList Entity Counts: 131072; ORM: FreeSql*

Elapsed: 00:00:00.6495301; Query Entity Counts: 131072; ORM: Dapper
```

[More..](https://github.com/2881099/FreeSql/wiki/%e6%80%a7%e8%83%bd)

## 👯 Contributors

<a href="https://contributors-img.web.app/image?repo=dotnetcore/FreeSql">
  <img src="https://contributors-img.web.app/image?repo=dotnetcore/FreeSql" />
</a>

And other friends who made important suggestions for this project, they include:

[systemhejiyong](https://github.com/systemhejiyong), 
[LambertW](https://github.com/LambertW), 
[mypeng1985](https://github.com/mypeng1985), 
[stulzq](https://github.com/stulzq), 
[movingsam](https://github.com/movingsam), 
[ALer-R](https://github.com/ALer-R), 
[zouql](https://github.com/zouql), 
深圳|凉茶, 
[densen2014](https://github.com/densen2014), 
[LiaoLiaoWuJu](https://github.com/LiaoLiaoWuJu), 
[hd2y](https://github.com/hd2y), 
[tky753](https://github.com/tky753), 
[feijie999](https://github.com/feijie999), 
constantine, 
[JohnZhou2020](https://github.com/JohnZhou2020), 
[mafeng8](https://github.com/mafeng8), etc.

## 💕 Donation

L*y 58元、花花 88元、麦兜很乖 50元、网络来者 2000元、John 99.99元、alex 666元、bacongao 36元、无名 100元、Eternity 188元、无名 10元、⌒.Helper~..oO 66元、习惯与被习惯 100元、无名 100元、蔡易喋 88.88元、中讯科技 1000元、Good Good Work 24元、炽焰 6.6元、Nothing 100元、兰州天擎赵 500元、哈利路亚 300元、
无名 100元、蛰伏 99.99元、TCYM 66.66元、MOTA 5元、LDZXG 30元、Near 30元、建爽 66元、无名 200元、LambertWu 100元、无名 18.88元、乌龙 50元

> Thank you for your donation

- [Alipay](https://www.cnblogs.com/FreeSql/gallery/image/338860.html)

- [WeChat](https://www.cnblogs.com/FreeSql/gallery/image/338859.html)

## 🗄 License

[MIT](LICENSE)
