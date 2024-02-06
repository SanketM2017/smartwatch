<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Digital Clock</title>
    <style>
        *
        {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        .wrapper
        {
            display: flex;
           justify-content: space-between;
            /* min-height: 200px; */
            color: black;
        }
        #wrapper
        {
            width: 50%;
            min-height: 200px;
            margin: 30vh auto;
            background-color: gray;
            padding: 20px;
            border-radius: 30px; 
        }
        .wrapper div
        {
            width: 32%;
            height: 200px;
            background-color:black;
            align-items: center;
            display: flex;
            font-size: 70px;
            color: white;
            box-shadow:  0px 0px 15px 5px white,inset 0px 0px 15px 5px white;
            border-radius: 20px;
            border: gray solid 1px;
        }
        .wrapper input
        {
            margin: 0 auto;   
            text-align: center;
            background-color: transparent;
            border:none;
            color:white;
            font-size: 50px;
            width: 100%;
        }
        #day
        {
            display: flex;
            justify-content: center;
            float: right;
            font-size: 30px;
            letter-spacing: 5px;
            margin-top: 20px;
            color: white;
            background-color: black;
            width: 60%;
            box-shadow:  0px 0px 15px 2px white,inset 0px 0px 15px 2px white;
            border: gray solid 1px;
            border-radius: 10px;

        }
        .clearfix::after
        {
            content: "";
            clear: both;
            display: block;
        }
        .animation
        {
            animation: flip 1s 1s forwards ease;
        }
        @keyframes flip {
            0%
            {
                transform: rotateX(0deg);
                
            }
            50%
            {
                transform: rotateX(180deg);
               
            }
            100%
            {
                transform: rotateX(360deg);
                color: transparent;
            }
        }
    </style>
    <script>
        function timeset()
        {
            let days=["Sun","Mon","Tue","Wed","Thur","Fri","Sat"]
            let time=new Date()
            let hd=(time.getHours()<10)? "0"+time.getHours():time.getHours()
            let md=(time.getMinutes()<10)? "0"+time.getMinutes():time.getMinutes()
            let sd=(time.getSeconds()<10)? "0"+time.getSeconds():time.getSeconds()
            let day=days[time.getDay()]
            let month=(time.getMonth()+1)<10 ? "0"+(time.getMonth()+1) : "0"+ (time.getMonth()+1) 
            let date=(time.getDate()<10) ? "0"+time.getDate():time.getDate()
            let dateall=date+"/"+month+"/"+time.getFullYear()
            document.getElementById("hr").value=hd
            document.getElementById("min").value=md
            document.getElementById("sec").value=sd
            document.getElementById("day").innerHTML=day+" , "+dateall
        }
        setInterval(timeset,1000)
        
    </script>
</head>
<body>
    <div id="wrapper" >
        <div class="wrapper">
        <div ><input type="text" readonly id="hr" ></div>
        <div ><input type="text" readonly id="min"></div>
        <div ><input type="text" readonly id="sec"></div>
    </div>
    <div class="clearfix">
        <p id="day"></p>
    </div>
    </div>
    
</body>
</html>
