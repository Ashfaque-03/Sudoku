var check
var nxtlvl
var btn=""
var idname="level1" // initially level one will present
var myInterval
var flag=0
var totalSeconds
var img=0

function settingShow()
{
    document.getElementById("right-opt").style.display = "block"
    document.getElementById("settingsBox").style.display = "flex"
    document.getElementById("num-box").style.display = "block"
}

function themeMenuHide()
{
    document.getElementById("settingsBox").style.display = "none"
}

function prev_slideBtn()
{
    img-=1
}
function nxt_slideBtn()
{
    img+=1
}

function bgImgSetting()
{
    let bg=img%3
    if(bg==0)
    {
        document.body.style.backgroundImage = "url('/assets/image/bg1.jpg')";
        document.getElementById("header").style.color = "black"
        document.body.style.backgroundSize = "cover";
    }
    if(bg==1)
    {
        document.body.style.backgroundImage = "url('/assets/image/bg2.jpg')";
        document.getElementById("header").style.color = "white"
        document.body.style.backgroundSize = "cover";

    }
    if(bg==2)
    {
        document.body.style.backgroundImage = "url('/assets/image/bg3.jpg')";
        document.getElementById("header").style.color = "white"
        document.body.style.backgroundSize = "cover";
    }
    document.body.style.backgroundRepeat = "no-repeat";
    document.body.style.backgroundSize = "cover";

}
function theme(color)
{
    
    if(color=='blue')
    {
        document.getElementById('header').style.color="rgba(var(--bs-primary-rgb)"
        // const inputBox = document.querySelectorAll('.inp');
        // inputBox.forEach(inp => { inp.style.borderColor= 'blue'});
        const multiBox = document.querySelectorAll('.box');
        multiBox.forEach(box => { box.style.borderColor= 'blue'});
    }
    else if(color== 'black')
    {
        document.getElementById('header').style.color="rgba(var(--bs-primary-rgb),var(--bs-bg-opacity))"
        // const inputBox = document.querySelectorAll('.inp');
        // inputBox.forEach(inp => { inp.style.borderColor= 'black'});
        const multiBox = document.querySelectorAll('.box');
        multiBox.forEach(box => { box.style.borderColor= 'black'});
    }
    else if(color=='orange')
    {
        document.getElementById('header').style.color="rgb(177, 121, 16)"
        // const inputBox = document.querySelectorAll('.inp');
        // inputBox.forEach(inp => { inp.style.borderColor= 'rgb(177, 121, 16)'});
        const multiBox = document.querySelectorAll('.box');
        multiBox.forEach(box => { box.style.borderColor= 'rgb(177, 121, 16)'});
    }
    else if(color=='yellow')
    {
        document.getElementById('header').style.color="rgb(154, 154, 13)"
        // const inputBox = document.querySelectorAll('.inp');
        // inputBox.forEach(inp => { inp.style.borderColor= 'rgb(154, 154, 13)'});
        const multiBox = document.querySelectorAll('.box');
        multiBox.forEach(box => { box.style.borderColor= 'rgb(154, 154, 13)'});
    }
    else if(color=='green')
    {
        document.getElementById('header').style.color="green"
        // const inputBox = document.querySelectorAll('.inp');
        // inputBox.forEach(inp => { inp.style.borderColor= 'green'});
        const multiBox = document.querySelectorAll('.box');
        multiBox.forEach(box => { box.style.borderColor= 'green'});
        
    }
    else if(color=='red')
    {
        document.getElementById('header').style.color="rgb(184, 7, 7)"        
        // const inputBox = document.querySelectorAll('.inp');
        // inputBox.forEach(inp => { inp.style.borderColor= 'rgb(184, 7, 7)'});
        const multiBox = document.querySelectorAll('.box');
        multiBox.forEach(box => { box.style.borderColor= 'rgb(184, 7, 7)'});
    }
    else
    {
        document.getElementById('header').style.color=color     ;   
        // const inputBox = document.querySelectorAll('.inp');
        // inputBox.forEach(inp => { inp.style.borderColor= color});
        const multiBox = document.querySelectorAll('.box');
        multiBox.forEach(box => { box.style.borderColor= color});
    }

}

// for focus function for all levels
function levelFocus()
{
    var levelbtn=idname+"Name"
    const numbers = document.querySelectorAll('.options');
    numbers.forEach(btn => { btn.style.color = 'rgb(183, 183, 183)'});
    document.getElementById(levelbtn).style.color = 'gold';
}

function PointerEventNone()
{
    var sudokubox= idname+"-box" //for each level working entering inputs
    if(check==0)
    {
        document.getElementById(sudokubox).style['pointer-events'] = 'none';
        document.getElementById("num-box").style['pointer-events'] = 'none';
    }
    else
    {
        document.getElementById(sudokubox).style['pointer-events'] = 'auto';
        document.getElementById("num-box").style['pointer-events'] = 'auto';
    }
    console.log(sudokubox)
}

function levelBtn(level)
{
    nxtlvl=1
    idname=level
    levelFocus()
    refresh() 
    const numbers = document.querySelectorAll('.levels');
    numbers.forEach(lvl => { lvl.style.display = 'none'});
    var options = document.getElementById(level);
    if (options.style.display === "none") 
    {
        options.style.display = "flex";

    }
    
    else 
    {
        options.style.display = "flex";
    }

}

function gameEnds()
{
    var lvlInp="."+idname+"-inp"
    const numbers = document.querySelectorAll(lvlInp);
    numbers.forEach(inp => { inp.setAttribute('disabled', '')});
}
function refreshOn()
{
    check=0
    var lvlInp="."+idname+"-inp"
    const numbers = document.querySelectorAll(lvlInp);
    numbers.forEach(inp => { inp.disabled==false? inp.value="":""}); 
    numbers.forEach(inp => { inp.style.backgroundColor = null});  
    clearInterval(myInterval);
    startShow()
    PointerEventNone()
    bgWhite()
    uncheckError()
    failStarColor()
}
function refresh()
{
    if(check==0)
    {
        refreshOn()
    }
    else if(check==1)
    {
        if(nxtlvl==1)
        {
            if(confirm("Are you sure you want to Refresh?")) //alert to refresh
            {
                refreshOn()
            }
        }
        else
        {
            if(confirm("Are you sure you want to move to next level? \nYour previous game will refresh.")) //alert to refresh
            {
                refreshOn()
                nxtlvl=0
            }
        }
    }
        
}

function retry()
{
    refresh()
    bgGreen()
    document.getElementById("win-box").style.display="none"
    document.getElementById("fail-box").style.display="none"
}

function bgGreen()
{
    document.getElementById("prevBtn").style.backgroundColor="green"
    document.getElementById("prevBtn").disabled=false
    document.getElementById("fail_prevBtn").style.backgroundColor="green"
    document.getElementById("fail_prevBtn").disabled=false
    document.getElementById("nxtBtn").style.backgroundColor="green"
    document.getElementById("nxtBtn").disabled=false
}

function nextLevel()
{
    refresh()
    bgGreen()
    document.getElementById("win-box").style.display="none"
    document.getElementById("fail-box").style.display="none"
    if(idname=="level1")
    {
        
        levelBtn("level2")
    }
    else if(idname=="level2")
    {
        levelBtn("level3")
    }
    else if(idname=="level3")
    {
        levelBtn("level4")
    }
    else if(idname=="level4")
    {
        levelBtn("level5")
    }
    else if(idname=="level5")
    {
        levelBtn("level6")
    }
    else if(idname=="level6")
    {
        levelBtn("level1")
    }
}
function prevLevel()
{
    refresh()
    bgGreen()
    document.getElementById("win-box").style.display="none"
    document.getElementById("fail-box").style.display="none"
    if(idname=="level1")
    {
        
        levelBtn("level1")
    }
    else if(idname=="level2")
    {
        levelBtn("level1")
    }
    else if(idname=="level3")
    {
        levelBtn("level2")
    }
    else if(idname=="level4")
    {
        levelBtn("level3")
    }
    else if(idname=="level5")
    {
        levelBtn("level4")
    }
    else if(idname=="level6")
    {
        levelBtn("level5")
    }
}

// result star showing
function winStar()
{
    var totalTime= 900
    var starTime =totalTime/5
    if((totalSeconds>0) && (totalSeconds<=(1*starTime)))
    {
        starColor(1)
    }
    else if((totalSeconds>(1*starTime)) && (totalSeconds<=(2*starTime)))
    {
        starColor(2)
    }
    else if((totalSeconds>(2*starTime)) && (totalSeconds<=(3*starTime)))
    {
        starColor(3)
    }
    else if((totalSeconds>(3*starTime)) && (totalSeconds<=(4*starTime)))
    {
        starColor(4)
    }
    else if((totalSeconds>(4*starTime)) && (totalSeconds<=(5*starTime)))
    {
        starColor(5)
    }
}
function failStarColor()
{
    for(let i=1; i<=5; i++)
    {
        stars="star"+i
        document.getElementById(stars).style.color = "grey"
    }
}

function starColor(count)
{
    for(let i=1; i<=count; i++)
    {
        stars="star"+i
        levelStars=idname+stars
        document.getElementById(stars).style.color = "goldenrod"
        document.getElementById(levelStars).style.color = "gold"
    }
}

function editMenu()
{
    var options = document.getElementById("right-opt");
    if (options.style.display == "none") 
    {
        options.style.display = "block";
        document.getElementById("num-box").style.display = "block"

    }
    
    else 
    {
        options.style.display = "none";
        document.getElementById("num-box").style.display = "none"

    }
}   

function muteUnmute()
{
    var mute = document.getElementById("mute");
    var unmute = document.getElementById("unmute");
    if (mute.style.display == "none") 
    {
        mute.style.display = "flex";
        unmute.style.display = "none";
        music.muted = true;
        music.pause();
    } 
    else 
    {
        mute.style.display = "none";
        unmute.style.display = "flex";  
        music.muted = false;   
        music.play();
                
    }
}

function BoxWiseCheck()
{
    // Checking 1-9 in box wise
    // box1
    var inpId_a=idname+"r1c1"
    var inpId_b=idname+"r1c2"
    var inpId_c=idname+"r1c3"
    var inpId_d=idname+"r2c1"
    var inpId_e=idname+"r2c2"
    var inpId_f=idname+"r2c3"
    var inpId_g=idname+"r3c1"
    var inpId_h=idname+"r3c2"
    var inpId_i=idname+"r3c3"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    
    // box2
    var inpId_a=idname+"r1c4"
    var inpId_b=idname+"r1c5"
    var inpId_c=idname+"r1c6"
    var inpId_d=idname+"r2c4"
    var inpId_e=idname+"r2c5"
    var inpId_f=idname+"r2c6"
    var inpId_g=idname+"r3c4"
    var inpId_h=idname+"r3c5"
    var inpId_i=idname+"r3c6"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // box3
    var inpId_a=idname+"r1c7"
    var inpId_b=idname+"r1c8"
    var inpId_c=idname+"r1c9"
    var inpId_d=idname+"r2c7"
    var inpId_e=idname+"r2c8"
    var inpId_f=idname+"r2c9"
    var inpId_g=idname+"r3c7"
    var inpId_h=idname+"r3c8"
    var inpId_i=idname+"r3c9"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // box4
    var inpId_a=idname+"r4c1"
    var inpId_b=idname+"r4c2"
    var inpId_c=idname+"r4c3"
    var inpId_d=idname+"r5c1"
    var inpId_e=idname+"r5c2"
    var inpId_f=idname+"r5c3"
    var inpId_g=idname+"r6c1"
    var inpId_h=idname+"r6c2"
    var inpId_i=idname+"r6c3"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // box5
    var inpId_a=idname+"r4c4"
    var inpId_b=idname+"r4c5"
    var inpId_c=idname+"r4c6"
    var inpId_d=idname+"r5c4"
    var inpId_e=idname+"r5c5"
    var inpId_f=idname+"r5c6"
    var inpId_g=idname+"r6c4"
    var inpId_h=idname+"r6c5"
    var inpId_i=idname+"r6c6"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // box6
    var inpId_a=idname+"r4c7"
    var inpId_b=idname+"r4c8"
    var inpId_c=idname+"r4c9"
    var inpId_d=idname+"r5c7"
    var inpId_e=idname+"r5c8"
    var inpId_f=idname+"r5c9"
    var inpId_g=idname+"r6c7"
    var inpId_h=idname+"r6c8"
    var inpId_i=idname+"r6c9"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // box7
    var inpId_a=idname+"r7c1"
    var inpId_b=idname+"r7c2"
    var inpId_c=idname+"r7c3"
    var inpId_d=idname+"r8c1"
    var inpId_e=idname+"r8c2"
    var inpId_f=idname+"r8c3"
    var inpId_g=idname+"r9c1"
    var inpId_h=idname+"r9c2"
    var inpId_i=idname+"r9c3"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // box8
    var inpId_a=idname+"r7c4"
    var inpId_b=idname+"r7c5"
    var inpId_c=idname+"r7c6"
    var inpId_d=idname+"r8c4"
    var inpId_e=idname+"r8c5"
    var inpId_f=idname+"r8c6"
    var inpId_g=idname+"r9c4"
    var inpId_h=idname+"r9c5"
    var inpId_i=idname+"r9c6"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // box9
    var inpId_a=idname+"r7c7"
    var inpId_b=idname+"r7c8"
    var inpId_c=idname+"r7c9"
    var inpId_d=idname+"r8c7"
    var inpId_e=idname+"r8c8"
    var inpId_f=idname+"r8c9"
    var inpId_g=idname+"r9c7"
    var inpId_h=idname+"r9c8"
    var inpId_i=idname+"r9c9"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
}

function rowCheck()   // checking 1-9 row wise
{
    // row 1
    var inpId_a=idname+"r1c1"
    var inpId_b=idname+"r1c2"
    var inpId_c=idname+"r1c3"
    var inpId_d=idname+"r1c4"
    var inpId_e=idname+"r1c5"
    var inpId_f=idname+"r1c6"
    var inpId_g=idname+"r1c7"
    var inpId_h=idname+"r1c8"
    var inpId_i=idname+"r1c9"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    
    // row 2
    var inpId_a=idname+"r2c1"
    var inpId_b=idname+"r2c2"
    var inpId_c=idname+"r2c3"
    var inpId_d=idname+"r2c4"
    var inpId_e=idname+"r2c5"
    var inpId_f=idname+"r2c6"
    var inpId_g=idname+"r2c7"
    var inpId_h=idname+"r2c8"
    var inpId_i=idname+"r2c9"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // row 3
    var inpId_a=idname+"r3c1"
    var inpId_b=idname+"r3c2"
    var inpId_c=idname+"r3c3"
    var inpId_d=idname+"r3c4"
    var inpId_e=idname+"r3c5"
    var inpId_f=idname+"r3c6"
    var inpId_g=idname+"r3c7"
    var inpId_h=idname+"r3c8"
    var inpId_i=idname+"r3c9"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // row 4
    var inpId_a=idname+"r4c1"
    var inpId_b=idname+"r4c2"
    var inpId_c=idname+"r4c3"
    var inpId_d=idname+"r4c4"
    var inpId_e=idname+"r4c5"
    var inpId_f=idname+"r4c6"
    var inpId_g=idname+"r4c7"
    var inpId_h=idname+"r4c8"
    var inpId_i=idname+"r4c9"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // row 5
    var inpId_a=idname+"r5c1"
    var inpId_b=idname+"r5c2"
    var inpId_c=idname+"r5c3"
    var inpId_d=idname+"r5c4"
    var inpId_e=idname+"r5c5"
    var inpId_f=idname+"r5c6"
    var inpId_g=idname+"r5c7"
    var inpId_h=idname+"r5c8"
    var inpId_i=idname+"r5c9"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // row 6
    var inpId_a=idname+"r6c1"
    var inpId_b=idname+"r6c2"
    var inpId_c=idname+"r6c3"
    var inpId_d=idname+"r6c4"
    var inpId_e=idname+"r6c5"
    var inpId_f=idname+"r6c6"
    var inpId_g=idname+"r6c7"
    var inpId_h=idname+"r6c8"
    var inpId_i=idname+"r6c9"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // row 7
    var inpId_a=idname+"r7c1"
    var inpId_b=idname+"r7c2"
    var inpId_c=idname+"r7c3"
    var inpId_d=idname+"r7c4"
    var inpId_e=idname+"r7c5"
    var inpId_f=idname+"r7c6"
    var inpId_g=idname+"r7c7"
    var inpId_h=idname+"r7c8"
    var inpId_i=idname+"r7c9"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // row 8
    var inpId_a=idname+"r8c1"
    var inpId_b=idname+"r8c2"
    var inpId_c=idname+"r8c3"
    var inpId_d=idname+"r8c4"
    var inpId_e=idname+"r8c5"
    var inpId_f=idname+"r8c6"
    var inpId_g=idname+"r8c7"
    var inpId_h=idname+"r8c8"
    var inpId_i=idname+"r8c9"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    // row 9
    var inpId_a=idname+"r9c1"
    var inpId_b=idname+"r9c2"
    var inpId_c=idname+"r9c3"
    var inpId_d=idname+"r9c4"
    var inpId_e=idname+"r9c5"
    var inpId_f=idname+"r9c6"
    var inpId_g=idname+"r9c7"
    var inpId_h=idname+"r9c8"
    var inpId_i=idname+"r9c9"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
}

function colCheck()   // checking 1-9 col wise
{
    // col 1
    var inpId_a=idname+"r1c1"
    var inpId_b=idname+"r2c1"
    var inpId_c=idname+"r3c1"
    var inpId_d=idname+"r4c1"
    var inpId_e=idname+"r5c1"
    var inpId_f=idname+"r6c1"
    var inpId_g=idname+"r7c1"
    var inpId_h=idname+"r8c1"
    var inpId_i=idname+"r9c1"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
    
    // col 2
    var inpId_a=idname+"r1c2"
    var inpId_b=idname+"r2c2"
    var inpId_c=idname+"r3c2"
    var inpId_d=idname+"r4c2"
    var inpId_e=idname+"r5c2"
    var inpId_f=idname+"r6c2"
    var inpId_g=idname+"r7c2"
    var inpId_h=idname+"r8c2"
    var inpId_i=idname+"r9c2"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }

    // col 3
    var inpId_a=idname+"r1c3"
    var inpId_b=idname+"r2c3"
    var inpId_c=idname+"r3c3"
    var inpId_d=idname+"r4c3"
    var inpId_e=idname+"r5c3"
    var inpId_f=idname+"r6c3"
    var inpId_g=idname+"r7c3"
    var inpId_h=idname+"r8c3"
    var inpId_i=idname+"r9c3"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }

    // col 4
    var inpId_a=idname+"r1c4"
    var inpId_b=idname+"r2c4"
    var inpId_c=idname+"r3c4"
    var inpId_d=idname+"r4c4"
    var inpId_e=idname+"r5c4"
    var inpId_f=idname+"r6c4"
    var inpId_g=idname+"r7c4"
    var inpId_h=idname+"r8c4"
    var inpId_i=idname+"r9c4"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }

    // col 5
    var inpId_a=idname+"r1c5"
    var inpId_b=idname+"r2c5"
    var inpId_c=idname+"r3c5"
    var inpId_d=idname+"r4c5"
    var inpId_e=idname+"r5c5"
    var inpId_f=idname+"r6c5"
    var inpId_g=idname+"r7c5"
    var inpId_h=idname+"r8c5"
    var inpId_i=idname+"r9c5"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }

    // col 6
    var inpId_a=idname+"r1c6"
    var inpId_b=idname+"r2c6"
    var inpId_c=idname+"r3c6"
    var inpId_d=idname+"r4c6"
    var inpId_e=idname+"r5c6"
    var inpId_f=idname+"r6c6"
    var inpId_g=idname+"r7c6"
    var inpId_h=idname+"r8c6"
    var inpId_i=idname+"r9c6"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }

    // col 7
    var inpId_a=idname+"r1c7"
    var inpId_b=idname+"r2c7"
    var inpId_c=idname+"r3c7"
    var inpId_d=idname+"r4c7"
    var inpId_e=idname+"r5c7"
    var inpId_f=idname+"r6c7"
    var inpId_g=idname+"r7c7"
    var inpId_h=idname+"r8c7"
    var inpId_i=idname+"r9c7"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }

    // col 8
    var inpId_a=idname+"r1c8"
    var inpId_b=idname+"r2c8"
    var inpId_c=idname+"r3c8"
    var inpId_d=idname+"r4c8"
    var inpId_e=idname+"r5c8"
    var inpId_f=idname+"r6c8"
    var inpId_g=idname+"r7c8"
    var inpId_h=idname+"r8c8"
    var inpId_i=idname+"r9c8"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }

    // col 9
    var inpId_a=idname+"r1c9"
    var inpId_b=idname+"r2c9"
    var inpId_c=idname+"r3c9"
    var inpId_d=idname+"r4c9"
    var inpId_e=idname+"r5c9"
    var inpId_f=idname+"r6c9"
    var inpId_g=idname+"r7c9"
    var inpId_h=idname+"r8c9"
    var inpId_i=idname+"r9c9"
    var a=document.getElementById(inpId_a).value
    var b=document.getElementById(inpId_b).value
    var c=document.getElementById(inpId_c).value
    var d=document.getElementById(inpId_d).value
    var e=document.getElementById(inpId_e).value
    var f=document.getElementById(inpId_f).value
    var g=document.getElementById(inpId_g).value
    var h=document.getElementById(inpId_h).value
    var i=document.getElementById(inpId_i).value
    var stringArray=[a,b,c,d,e,f,g,h,i]
    var numberArray=[]
    console.log(numberArray)
    length = stringArray.length;
    for (let i = 0; i < length; i++)
    {
        numberArray.push(parseInt(stringArray[i]));
    }
    countCheck_obj={}
    for(let i=0; i<numberArray.length; i++)
    {
        for(let j=0; j<numberArray.length; j++)
        {
            if(i==j)
            {
                continue
            }
            
            else
            {
                if(numberArray[i]==numberArray[j])
                {
                    console.log(numberArray[i],"at",i,",",j)
                    // repeatAction(i)
                    if(i==0)      { document.getElementById(inpId_a).style.color="red"}
                    else if(i==1) { document.getElementById(inpId_b).style.color="red"}
                    else if(i==2) { document.getElementById(inpId_c).style.color="red"}
                    else if(i==3) { document.getElementById(inpId_d).style.color="red"}
                    else if(i==4) { document.getElementById(inpId_e).style.color="red"}
                    else if(i==5) { document.getElementById(inpId_f).style.color="red"}
                    else if(i==6) { document.getElementById(inpId_g).style.color="red"}
                    else if(i==7) { document.getElementById(inpId_h).style.color="red"}
                    else if(i==8) { document.getElementById(inpId_i).style.color="red"}
                }
            }
        }
    }
}

function uncheckError()
{

    const numbers = document.querySelectorAll('.inp');
    numbers.forEach(inp => { inp.style.color = 'black'});
}
function hint(){
    if(check==1)
    {
        BoxWiseCheck(),
        rowCheck(),
        colCheck()
    }
}
function numBoxCheck()
{
    
}

//  showing valules to input field

function showValue(num)
{
    bgBlack(num)
    console.log(num)
    var lvlInp="."+idname+"-inp"
    const numbers = document.querySelectorAll(lvlInp);
    numbers.forEach(inp => { inp.style.backgroundColor = null});    
    var count=0
    for(inp of numbers)
    {
        if(inp.value==num)
        {
            count+=1
            console.log(num) //shows how many times repeated
            inp.style.backgroundColor='green'
        }
        
    }
    if(count>9)
    {
        bgRed(num)
        count=0
    } 
    else if(count==0)
    {
        numbers.forEach(inp => { inp.style.backgroundColor = null});    
        console.log(num) //shows how many times repeated
    }
}
// for focusing the num-btn black background
function bgBlack(num)
{
    bgWhite()
    if(num=='1')
    {
        document.getElementById("num1").style.backgroundColor = "black";  
        document.getElementById('num1').style.color="white"  
    }
    if(num=='2')
    {
        document.getElementById("num2").style.backgroundColor = "black";  
        document.getElementById('num2').style.color="white"  
    }
    if(num=='3')
    {
        document.getElementById("num3").style.backgroundColor = "black";  
        document.getElementById('num3').style.color="white"  
    }
    if(num=='4')
    {
        document.getElementById("num4").style.backgroundColor = "black";  
        document.getElementById('num4').style.color="white"  
    }
    if(num=='5')
    {
        document.getElementById("num5").style.backgroundColor = "black";  
        document.getElementById('num5').style.color="white"  
    }
    if(num=='6')
    {
        document.getElementById("num6").style.backgroundColor = "black";  
        document.getElementById('num6').style.color="white"  
    }
    if(num=='7')
    {
        document.getElementById("num7").style.backgroundColor = "black";  
        document.getElementById('num7').style.color="white"  
    }
    if(num=='8')
    {
        document.getElementById("num8").style.backgroundColor = "black";  
        document.getElementById('num8').style.color="white"  
    }
    if(num=='9')
    {
        document.getElementById("num9").style.backgroundColor = "black";  
        document.getElementById('num9').style.color="white"  
    }
    if(num=='0')
    {
        document.getElementById("num0").style.backgroundColor = "black";  
        document.getElementById('num0').style.color="white"  
    }
}

// for focusing the num-btn black background
function bgWhite()
{
    const numbers = document.querySelectorAll('.num-btn');
    numbers.forEach(btn => { btn.style.backgroundColor = "white"});  
    numbers.forEach(btn => { btn.style.color = "black"});  
}

// for red color error for more than 9 count for each number
function bgRed(num)
{
    const numbers = document.querySelectorAll(lvlInp);
    numbers.forEach(inp => { inp.style.backgroundColor = null});    
    for(inp of numbers)
    {
        if(inp.value==num)
        {
            console.log(inp.style.backgroundColor='red') //shows how many times repeated
            inp.style.backgroundColor='red'
        }
        
    }
}

//   Result      Result         Result      Result          Result          Result          Result          Result          Result          Result      Result
function result()
{
    if(check==1)
    {
        var lvlInp="."+idname+"-inp"
        const numbers = document.querySelectorAll(lvlInp);
        numbers.forEach(inp => { inp.value ==""? flag=1 : ""});
        if (flag == 1)
        {
        alert("Please input a Value");
        // clearInterval(setInterval());
        flag=0
        }
        else 
        {
            clearInterval(myInterval);
            finalResult()
        }
    }
}

function TimeoutAlert()
{
    var txt;
alert("Oops! Timeout")
    timeOutResult()
}
function timeOutResult()
{
    const numbers = document.querySelectorAll('.inp');
    numbers.forEach(inp => { inp.value ==""? flag=1 : count=1});
    if (flag == 1)
    {
        document.getElementById("fail-box").style.display="block"
    }
    else 
    {
        finalResult()
    }
}

function finalResult()
{
    check=0
    BoxWiseCheck()
    rowCheck()
    colCheck()
    PointerEventNone()
    var lvlInp="."+idname+"-inp"
    const numbers = document.querySelectorAll(lvlInp);
    var color1=""
    numbers.forEach(inp => { inp.style.color =="red"? color1="red" : ""});
    
    if(color1=="red")
    {
        color1=""
        document.getElementById("fail-box").style.display="block"
    }
    else
    {
        color1=""
        winStar()
        document.getElementById("win-box").style.display="block"
    }
    if(idname=="level1")
    {
        document.getElementById("prevBtn").style.backgroundColor="grey"
        document.getElementById("prevBtn").disabled=true
        document.getElementById("fail_prevBtn").style.backgroundColor="grey"
        document.getElementById("fail_prevBtn").disabled=true
    }
    if(idname=="level6")
    {
        document.getElementById("nxtBtn").style.backgroundColor="grey"
        document.getElementById("nxtBtn").disabled=true
    }
}

// show startbtn
function startShow()
{
    var timercount = document.getElementById("countdown");
    var options = document.getElementById("startGame");
            if (options.style.display == "none") 
            {
                options.style.display = "flex";
                timercount.style.display = "none";
            }
            
            else 
            {
                options.style.display = "flex";
                timercount.style.display = "none";
            }    
}

//hide start btn
function startHide() 
{
    var timercount = document.getElementById("countdown");
    var options = document.getElementById("startGame");
            if (options.style.display == "none") 
            {
                options.style.display = "flex";
                timercount.style.display = "none";
            }
            
            else 
            {
                options.style.display = "none";
                timercount.style.display = "flex";
            }    
}

// time out timer
function timeOut()
{

    check=1
    document.getElementById("right-opt").style.display = "block"
    document.getElementById("num-box").style.display = "block"
    PointerEventNone()
    startHide() //hide start btn

    let days = 0; //starting number of days
    let hours = 0; // starting number of hours
    let minutes = 15; // starting number of minutes
    let seconds = 0; // starting number of seconds

    // converts all to seconds
    totalSeconds =
    days * 60 * 60 * 24 + hours * 60 * 60 + minutes * 60 + seconds;

    //temporary seconds holder
    let tempSeconds = totalSeconds;

    // calculates number of days, hours, minutes and seconds from a given number of seconds
    const convert = (value, inSeconds) => {
    if (value > inSeconds) {
        let x = value % inSeconds;
        tempSeconds = x;
        return (value - x) / inSeconds;
    } else {
        return 0;
    }
    };

    //sets seconds
    const setSeconds = (s) => {
    document.querySelector("#seconds").textContent = s + "s";
    };

    //sets minutes
    const setMinutes = (m) => {
    document.querySelector("#minutes").textContent = m + "m";
    };

    //sets hours
    const setHours = (h) => {
    document.querySelector("#hours").textContent = h + "h";
    };

    //sets Days
    const setDays = (d) => {
    document.querySelector("#days").textContent = d + "d";
    };
    
    // Update the count down every 1 second
    myInterval = setInterval(() => {
    //clears countdown when all seconds are counted
    if (totalSeconds <= 0) {
        check=0
        clearInterval(myInterval);
        TimeoutAlert()

        PointerEventNone()
    }
    setDays(convert(tempSeconds, 24 * 60 * 60));
    setHours(convert(tempSeconds, 60 * 60));
    setMinutes(convert(tempSeconds, 60));
    setSeconds(tempSeconds == 60 ? 59 : tempSeconds);
    totalSeconds--;
    tempSeconds = totalSeconds;
    }, 1000);
    console.log(totalSeconds)
}

// function delete inputs btn value
function del_InpValue()
{
    var btn="del" 
    document.getElementById('delBtn').style.borderColor="red"  
}
