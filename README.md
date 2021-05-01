# Algorithm
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<!DOCTYPE html>
<style type="text/css">

body {
	margin: 0px;
	position: relative;
	width:100%;
	
}


#wrap{
	padding-top:50px;

}

#id{
	font-size: 20px;
	font-weight: bold;
}

#head{
	float:right;
	text-align:right;
	width:300px;
}

#question{
	position:relative;
	padding-top:20px;
	padding-left:20px;
	height:200px;
	border: none;	
	outline:none;
	margin:0 auto;
	
	
	}	
	
input[name=answer1]{
	background-color: rgb(231, 76, 60);
	}	
	
input[name=answer2]{
	background-color: rgb(46, 204, 113);
	}
	
input[name=answer1], [name=answer2]{
	height:70px;
	border-radius: 5px;
	border : none;	
	font-size : 25px;
	display:inline-block;
	cursor: pointer;
	text-align:center;
    vertical-align:middle;
  	margin : 0 20px;
  	margin-bottom: 20px;
}	

#buttons{
	text-align: center;
	margin-top:100px;
	margin-bottom: 50px;
}

input[type=textarea]{
	height: 70%;
}

#content {
	margin: 0 auto;
	padding: 10px;
	top:50%;
	left:70%;
	width:70%
} 

.table_context {
	box-sizing: content-box;
	height: 400px;
	margin:0 auto;
	border: 2px solid #dddddd;
	border-radius: 5px;  
	position: relative;
}
    	
#viewAndtime{
	display: inline-block;
	text-align: right;
}

#title{
	width:300px;
	display: inline-block;
	text-align:left;
	font-size: 45px;
}

#tolist{
	width:100px;
	text-align: center;
}

a{
	margin-top:10px;
	text-decoration: none;
	color:black;
	font-size: 20px;
	float: right;
}

#chart{
	text-align:center;
	width: 100%;
	margin-left:180px;
	padding:auto auto;	
	
}

</style>
<body>
<%@ include file="view/header.jsp" %>
<form action="boardRegister.do" method="post" style="border:1px soild #ccc" id=content>
	<input type="hidden" name="user_idx" value="${vo.userIdx}">
		<div id="wrap">
           <div id="head">
		       <h3>번호 : ${board.boardIdx}</h3><span id="viewAndtime">등록시간 : ${board.registerDatetime} 조회수 : ${board.viewCount}</span> 
		   </div>    		     
		   <div id="title">
			   	${board.title}
		   </div>   
    		<div class="table_context">
	    		<div id="question">	
	    			${board.question}
	    			<div id="chart">
	    				<%@ include file="chart.jsp" %>
	    			</div>
	    		</div>
	    		
	    		<div id="buttons">
	                <input type="button" name="answer1" maxlength="10" value="${board.answer1}" style="width: 200px"; required>
	                <font size="10"><b>VS</b></font>
	                <input type="button" name="answer2" maxlength="10" value="${board.answer2}" style="width: 200px"; required>
	            </div>
	    	</div>
    	<a href="board_list.jsp">목록으로</a>
    </div>	 
</form>
<%@ include file="view/footer.jsp" %>
</body>
</html>
