# ksystem

# 1. 메일 전송 
```
select * from _TCASendMessage
select top 10 *  from _TCASendedMessage order by CrDateTime desc
select top 3 *  from _TCAFailedMessage order by CrDateTime desc

insert into _TCASendMessage
(
    CompanySeq      ,SendMessageID   ,SendUserSeq     ,SendMessageType ,Subject         ,
    SendMessage     ,RecvUserSeq     ,IsMemo          ,IsMail          ,IsSMS           ,
    SendMemo        ,SendMail        ,SendSMS         ,MemoDateTime    ,MailDateTime    ,
    SMSDateTime     ,TblKey          ,CrDateTime      ,AttachFiles     ,RecvEmail       ,
    RecvTelNo       ,SendEmail       ,CCEmail         ,AttachMessage   ,AttachFileName  ,
    AttachType      ,AttachConfig    ,States          ,Result          ,charset         ,
    EmailPass       ,IsFast          ,IsProcessing    ,JumpData        ,JumpMode        ,
    LoginPwd        ,MessageGroupSeq ,PgmSeq          ,SendTelNo       ,ToPgmSeq        ,
    BCCEmail        ,SecuBody        ,SendDateKey     ,ViewerId        ,ViewerValue     ,
    BisDivCode      ,IsAlimTalk      
)
select 1                            AS CompanySeq,	
       ISNULL((SELECT MAX(SendMessageID) FROM _TCASendMessage),0)+1 AS SendMessageID,	
       --ISNULL((SELECT TOP 1 UserSeq FROM _TCAUser WHERE UserName = '김보라'),0) AS SendUserSeq,	
       27520                        AS SendUserSeq, -- select * from _TCAUser where UserSeq = 27205
       1                            AS SendMessageType,	
       N'test'                      AS Subject,	
       N'테스트입니다.'             AS SendMessage,	
       0                            AS RecvUserSeq,	
       0,	1,	0,	
       0,	0,	0,	
       '1900-01-01 00:00:00.000'    AS MemoDateTime,	
       '2023-04-26 13:51:44.920'    AS MailDateTime,	
       '1900-01-01 00:00:00.000'    AS SMSDateTime,	
       ''                           AS TblKey,	
       '2023-04-26 13:51:42.853'    AS CrDateTime,	
       NULL                         AS AttachFiles,	
       'oni@abworld.co.kr'          AS RecvEmail,	
       NULL                         AS RecvTelNo,	
       'sc-cwkim@ksystem.co.kr'     AS SendEmail,	
       NULL,	NULL,	NULL,	
       0,	NULL,	'',	'',	NULL,	
       NULL,	NULL,	NULL,	NULL,	NULL,	
       NULL,	NULL,	NULL,	'00000000000',	NULL,	
       NULL,	NULL,	NULL,	NULL,	NULL,	
       NULL,	NULL
```
