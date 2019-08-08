# sql
# 字符统计
--------------
USE [mtAppBBSG]
GO
/****** Object:  UserDefinedFunction [dbo].[fn_charCount]    Script Date: 2019/8/8 18:29:56 ******/
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO




ALTER FUNCTION [dbo].[fn_charCount]
(
@str nvarchar(1),		--要统计的字符
@oStr nvarchar(max)     --字符串
)
RETURNS int
AS
BEGIN
   declare @i_start  int =1
   declare @i_cnt int=0
	while(CHARINDEX(@str,@oStr,@i_start)!=0) begin
	

	set @i_start=CHARINDEX(@str,@oStr,@i_start)+1
	set @i_cnt=@i_cnt+1;

	end

		
	RETURN @i_cnt
END
--------------------
