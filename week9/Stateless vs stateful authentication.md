# Stateless vs stateful authentication


### * What is session based authentication (stateful)?
Cookie based authentication is stateful. This means that an authentication record or session must be kept both on the server and client-side. The server needs to keep track of active sessions in a database (i.e the <b>'state'</b> of each particular user), while on the front-end a cookie is created that holds a session identifier, thus the name cookie based authentication. 

#### <u>How this works:</u>
1) User enters their login credentials
2) Server verifies the credentials are correct and creates a session which is then stored in a database
3) A cookie with the session ID is placed in the users browser
4)  On subsequent requests, the session ID is verified against the database and if valid the request processed
5)  Once a user logs out of the app, the session is destroyed both client and server side


#### <u>flow diagram:</u>
![](https://i.imgur.com/BcMfCld.png)






------------------------ 

### * What is token based authentication (stateless)?
Token-based authentication enables users to obtain a token that allows them to access a service and/or fetch a specific resource without using their username and password to authenticate every request. No 'state' is required to be held for them on the backend, and therefore the session as seen to be <b>'stateless'</b>.

#### <u>How this works:</u>
1)  User enters their login credentials
2) Server verifies the credentials are correct and returns a signed token
3)  This token is stored client-side, most commonly in local storage - but can be stored in session storage or a cookie as well
4)  Subsequent requests to the server include this token as an additional Authorization header or through one of the other methods mentioned above
5) The server decodes the JWT and if the token is valid processes the request
6)  Once a user logs out, the token is destroyed client-side, no interaction with the server is necessary.




#### <u>flow diagram:</u>
![](https://i.imgur.com/ERF2dSW.png)

-------------------------------

### Stateful vs  Stateless
  
  <i>What are the advantages and disadvantages of each?</i>

<table>
<thead>
    <td></td>
    <td><b>Stateful</b></td>
    <td><b>Stateless</b></td>
</thead>
<tr>
<td>Revoking Sessions</td>
<td>👍 <b>Can revoke the session anytime</b></td>
    <td>👎 Cannot revoke the session until token expiry</td>
</tr>
<tr>
    <td>Session Modification</td>
    <td>👍 <b>Session data can be changed later as we have access to it from the server side</b></td>
    <td>👎 Session data cannot be changed ('refreshed') until its expiration time</td>
</tr>

<tr>
    <td>Complexity</td>
    <td colspan="2"><b>The complexity depends on how your application and preference - stateless tends to be better for larger apps with lots of users, stateful for simple smaller apps</b></td>
</tr>
<tr>    
    <td>Memory & Resources</td>
    <td>👎 Uses more server side memory & resources</td>
    <td>👍 <b>Uses less memory on the server as info stored user-side</b></td>   
</tr>
tr>
    <td>Scalability</td>
    <td>👎 Harder and more expensive to scale</td>
    <td>👍 <b>Much more versitile and scalable</b></td>   
</tr>
<tr>
    <td>Server Farms
    (multiple servers)</td>
    <td>👎 Each server has to deal with a specific user once session created (or sync sessions across servers)</td>     
    <td>👍<b> Any server can deal with any request as info is held user-side</b></td>     
</tr>
<tr>
    <td>Security</td>
    <td>👍 <b>Server retains control over session infomation and therefore this can only be edited with direct access to server</b></td>     
    <td>👎 Although JWT is highly encrypted, tokens still sit outside of server control and therefore could be tampered with</td>     
</tr>
<tr>
    <td>Intergration with 3rd parties</td>
    <td>👎 As data is held on your backend, user authentication cannot as easily be passed on to other parties as it is stuck in your server </td>     
    <td>👍 <b>3rd parties can more easily check authntication of your users by utilising shared secrets on user web tokens</b></td>     
</tr>
<tr>
    <td>Session Expiry</td>
    <td>👎 Sometimes expiring sessions cause issues that are hard to find</td>     
    <td>👍 <b>no sessions are involved</b></td>     
</tr>
<tr>
    <td>Linking resources</td>
    <td>👎 Some sites store the ID of what the user is looking at in the sessions. This makes it impossible for users to simply copy and paste the URL or share it</td>     
    <td>👍<b> ensures the user can view the same page another user is viewing</b></td>     
</tr>

</table>


  



## Further Reading
- [[article] Stateless vs Stateful Introduction - 5 min article](https://medium.com/@kennch/stateful-and-stateless-authentication-10aa3e3d4986 )
- [[video] Stateful & Stateless servers - 7 min video](https://www.youtube.com/watch?v=FmctmpybIKs)
- [[video] Difference between Cookies & Tokens in Sessions - 9 min video](https://www.youtube.com/watch?v=44c1t_cKylo)
- [[article] Stateful and Stateless Applications Best Practices and Advantages](https://www.xenonstack.com/insights/stateful-and-stateless-applications/)
- [[article] Stateful and stateless authentication](https://medium.com/@kennch/stateful-and-stateless-authentication-10aa3e3d4986)
- [[Longer article on Stateless/Stateful]](https://www.xenonstack.com/insights/stateful-and-stateless-applications)
- [[Coursea] - stateless vs stateful](https://www.coursera.org/lecture/cloud-services-java-spring-framework/load-balancing-stateless-vs-stateful-applications-Yxrt5)
