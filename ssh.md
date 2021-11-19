# SSH 로그인 접속 시 퍼미션 문제 (UNPROTECTED PRIVATE KEY FILE)
ue
잘못된 퍼미션으로 SSH 로그인 접속 시 위와 같은 같은 에러가 났다. 

```
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
@         WARNING: UNPROTECTED PRIVATE KEY FILE!          @
@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
Permissions 0644 for '/Users/username/.ssh/your-key.pem' are too open.
It is required that your private key files are NOT accessible by others.
This private key will be ignored.
```

private key의 퍼미션이 너무 공개되어 있어서 생긴 문제였다. 해당 private key의 퍼미션을 644에서 600으로 바꿔서 해결하였다.

```
chmod 600 ~/.ssh/your-key.pem
```

 
## .ssh 폴더 내 퍼미션
.ssh 폴더 및 하위 파일들의 올바른 퍼미션은 다음과 같다.

```
chmod 700 ~/.ssh
chmod 600 ~/.ssh/id_rsa
chmod 644 ~/.ssh/id_rsa.pub  
chmod 644 ~/.ssh/authorized_keys
chmod 644 ~/.ssh/known_hosts
```
<div align=right>
by <a href='https://github.com/rangyu/TIL/blob/master/ubuntu/SSH-로그인-접속-시-퍼미션-문제-UNPROTECTED-PRIVATE-KEY-FILE.md'>rangyu</a>
</div>

---

**Depending on the system you are in! When you first try to connect! A vscode-server will be set up and configured on your server!**

In linux that can be in `/Home/<user>/.vscode-server` !

If you are on windows check what that is!

The first solution is to try the extension command: `Remote-SSH: kill VS Code Server on Host`

Open the command pallet (`CTRL + SHIFT + P` or `COMMAND + SHIFT + P` (mac) ).

And type `Remote kill` :
![image](https://i.stack.imgur.com/Coa06.png)

Then try to connect again! (That will kill the server on the host! Which will make it start again on the next try)

If that **doesn't work! And still failing!**

## Delete, rm

Then a good solution that can work is: to connect to your server through terminal (vscode terminal, gnome-terminal, whatever)! Then go and **remove** `/Home/<user>/.vscode-server`

Try to connect after it! At the attempt the server will be re-installed completly all anew! And good chances it will works! (I did that and it worked! So whatever that was going wrong on the vscode-server! you start all over! And the state or whatever go a new and problem resolved!

However you **loose things, config, meta data,** ... (you start a new!) In my case it didn't matter!

One can explore the **.vscode-server structure**, and elements! And you can save some part that you bring up later! (I didn't check!) (may do later)! It's an option!

<div align=right>
by <a href='https://stackoverflow.com/questions/64034813/vs-code-remote-ssh-connection-not-working'>stackoverflow</a>
</div>
