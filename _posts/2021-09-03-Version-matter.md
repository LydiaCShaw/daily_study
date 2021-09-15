---
layout: post
read_time: true
show_date: true
title: "Version is matter"
date:   2021-09-03 12:32:20 -0600
description: Using 
img: posts/20210816/cover.jpg
tags: [MATLAB, python, SQL server]
author: Lydia Shaw
github:  LydiaCShaw
mathjax: yes
---
I usually hear someone says ' Oh my god, my system/cell phone needs update again! I just installed the new version last week!'

Indeed, no matter EMUI or Windows, they propose new version very frequently. However, most of people may do not update on time, because when we update the software or system, we need to download the package, install them and wait for a long time. Besides, most of people used crack version for free, rather than membership, for these software, we may delete and replace some dll files, install without internet, find out activate code... which means updating is troublesome, just like me, I have fall behind many versions now.

Apparently, companies also think about this situation and propose the automatic update. However, another issue is that, when we work for a long time and intend to take a relax, how can we avoid the automatic update when computer standby?

I ever encountered this problem, even due to the compatibility issue, my laptop suffered a bug. Afterwards, when I finished my dinner, what I saw was not the article I was writing, but a 'blue screen' with error message.

Since then, I replaced my old laptop, and set the 'never update automatically' option. May be I have suffered from the PTSD of 'update'.

However, should we avoid installing new version?

Recently, we put the sensor into the brace to observe whether the brace for patients works or not and where do we attach the sensor can obtain more accurate data.

At that time, we encountered a problem: once the cell phone connected to the sensor by using bluetooth, even the operator disconnected cell phone connection, the sensor still was occupaied. However, that isn't today I want to talk about, I just explain this story for you.

Afterwards, we collected txt data from sensor, and I tried to use MATLAB to visualize to the curve.

![image](.\assets\img\posts\20210816\brace.png)

Professor proposed that it may be more clearly to compare this two sensors and the correlationship between temperature and force that using only one graph and marking double y axis both left and right hand sides.

I tried to search this kind of graph on Google, someone illustrated on CSDN that using function `yyaxis left`and `yyaxis right` can realize.

However, when I programmed on my own, I failed. And I found that this function occured after 2016b, but my version is 2015b.

Therefore, I have to find out some alternative codes or functions, which is troublesome.

`plotyy()` is the pre-version of `yyaxis`, it should be used like this format:
```javascript
[hAx1,hLine1,hLine2]=plotyy(x,y1,x,y2);
```
![image](.\assets\img\posts\20210816\brace2.jpg)

Another problem is when I used this function, the legend always dispalied wrong. 

All in all I spent more time solving this problem than just updating, let alone the result didn't satisfiesed me. So I think the best solution is istalling the new version.

### Version is matter?

This experience reminded me of my awful memory of learning python. Actually, not every version is perfect, and the new function may not be useful as the designer as he imagine. When you do more, you're wrong more. Therefore, the feeling of updating is just like a lottery. Sometimes I feel pleasantly surprised, sometimes I feel very disappointed.

When it comes to python, I encounted many errors because of the conflict of version. It seems that after renewing, some codes would have changed. Most of time, even I used codes from a programming book, which is correct and run successfully on the author's computer, I still have many errors.

Another story is when I downloaded and installed the SQL server, the newest version always installed failure. So I have to try the older version.Due to the language problem, finally I chose Wampserver instead.

![image](.\assets\img\posts\20210816\localhost.jpg)
![image](.\assets\img\posts\20210816\phpadmain.jpg)

Wampserver can run the SQL service alone, and it is also available for importing data from Excel. It is very convenient but we may also need to change the format from `xls` or `xlsx` from `csv`.

If we still used SQL to import Excel data, let's go through [this](https://docs.microsoft.com/zh-cn/sql/relational-databases/import-export/import-data-from-excel-to-sql?view=sql-server-ver15) website to explore more.

### Front-end and Back-end


First we should prepare a domain and a server. Domain can be  bought on Tecent Cloud, the price is around 2-5000RMB even more. 

If you don't have these above, that is no problem. Click [here](https://blog.csdn.net/qq_45073256/article/details/115501877?utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7EBlogCommendFromMachineLearnPai2%7Edefault-1.control) to see how to get the ip address by running cmd.

Of course, we used this way just for practicing and learning. If we want to connect to Internet, we must have a domain and we must set a complicated passward for admin in case it is cracked by hackers.That is very important.

The website I shared has a good example to display how to connect front-end and back-end, therefore,I just post some codes to record.


* back-end login java


```javascript
//import net.sf.json.JSON;
//import net.sf.json.JSONObject;

import javax.jws.WebService;
import javax.servlet.Servlet;
import javax.servlet.ServletConfig;
import javax.servlet.ServletRequest;
import javax.servlet.ServletResponse;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

import java.io.IOException;
import java.io.PrintWriter;
import java.io.Writer;
import java.sql.*;
@WebServlet("/login")
public class Database extends HttpServlet implements Servlet{
    private static final String JDBC_DRIVER = "com.mysql.cj.jdbc.Driver";
    private static final String DB_URL = "jdbc:mysql://localhost:3306/book?serverTimezone=UTC";
    private static final String USER_NAME = "root"; //用户名，一般都是root
    private static final String PASSWORD = "123456"; //数据库密码，根据自己数据库密码进行更改
    private static final String METHOD_GET = "GET";

    @Override
    protected void doGet(HttpServletRequest req, HttpServletResponse resp) throws ServletException, IOException {
    //        通过http协议获取前端提交过来的数据
        Connection conn = null;
        Statement stmt = null;
        String sql;
        ResultSet rs = null;

        resp.setContentType("text/html;charset=UTF-8");
        /* 设置响应头允许ajax跨域访问 */
        resp.setHeader("Access-Control-Allow-Origin", "*");
        /* 星号表示所有的异域请求都可以接受， */
        resp.setHeader("Access-Control-Allow-Methods", "GET,POST");

        PrintWriter out = resp.getWriter();
        Writer oout = resp.getWriter();
        
        try {
            Class.forName(JDBC_DRIVER);
            conn = DriverManager.getConnection(DB_URL, USER_NAME, PASSWORD);
            stmt = conn.createStatement();
            String user = "";
            String pwd = "";
            String success = null;
            String id = (String)req.getParameter("user");//通过容器的实现来取得通过get或者post方式提交过来的数据，这里均是get方法
            String password = (String)req.getParameter("pwd");
            System.out.println(id+password);
            sql = "select pwd from login where user = '"+id+"'"; //在数据库中查找相同id的密码
            rs = stmt.executeQuery(sql);

            while(rs.next()){
                pwd = rs.getString("pwd");
                System.out.println(pwd);
                if( pwd.equals(password)&&password!=null){//若从前端得到的密码与数据库中密码一致时返回成功
                    success = "1";
                    oout.write(success);
                }

            }
            if(success == null){
                oout.write("0");
            }

            rs.close();
            stmt.close();
            conn.close();
            out.close();

        } catch (ClassNotFoundException | SQLException e) {
            e.printStackTrace();
        } finally {

        }
    }

    @Override
    public void init(ServletConfig servletConfig) throws javax.servlet.ServletException {

    }

}


```

* login  wxml for an example.


```javascript
<view class="login_wrap">
    <view class="user_id">
        账号： <input placeholder="请输入您的账号" bindinput="handleInputId" value="{{userid}}"/>
    </view>
    <view class="user_password">
        密码： <input placeholder="请输入您的密码"  bindinput="handleInputPassword" value="{{userpassword}}"/>
    </view>
    <view class="login_register">
        <button class="login" plain="{{true}}" bindtap="handleLogin">登录</button>
    </view>
</view>
```
* login js

```javascript
Page({
  data:{
      id: '',
      password: '',
      userid: '',
      userpassword: '',
  },

  handleInputId(e){ //获取输入框中的信息，并保存到data中
    this.data.id = e.detail.value;
    //console.log(e.detail.value);
    
  },
  handleInputPassword(e){ //获取输入框中的信息，并保存到data中
    this.data.password = e.detail.value;
    //console.log( e.detail.value);
    
  },

  handleLogin(){ //点击登录时
      const id = this.data.id;
      const password = this.data.password;
      wx.request({	//向后端发送请求
          url: 'http://localhost:8080/data', //这里的地址可以填最开始查到的无线网的ip  10.65.206.5 也可以直接填localhost本机地址
          data:{
              userid: id,
              userpassword: password
          },
          success: (result)=>{
              console.log(result);
              if(result.data === "失败"){
                  wx.showToast({
                      title: '登陆失败',
                      icon: 'none',
                      duration: 2000,
                      mask: true,
                  });
                  this.setData({
                    userid:'',
                    userpassword:'',
                 })//登录失败清空输入框中的数据
              } else{
                wx.showToast({
                    title: '登陆成功',
                    icon: 'none',
                    duration: 2000,
                    mask: true,
                });
              }
              
          },
          fail: ()=>{},
          complete: ()=>{}
      });
  },
})

```









 
 
