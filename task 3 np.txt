var rq=new XMLHttpRequest();
rq.open('GET','https://restcountries.eu/rest/v2/all',true);
rq.send();
rq.onload=function (){
    var country=JSON.parse(this.response);
    for(var i in country){
        try{
         var cname=country[i].name;
         var latlong=country[i].latlng;
         if(latlong==0) {
             ("Lattitue and long not found");
         }
         weatherdata(cname,...latlong);
        }
        catch(e){
        console.log("invalid coordiantes"+cname);
        }
    }
}
var weatherdata=function(name,lat,lng){
    console.log(lat,lng);
    var request= new XMLHttpRequest();
var URL=`https://api.openweathermap.org/data/2.5/weather?lat=${lat}&lon=${lng}&appid=d0b86f6466536ab96e5e54155ded040c`;

request.open('GET',URL,true);
request.send();
request.onload=function(){
    var data=JSON.parse(this.response);
    console.log(name+" "+data.main.temp);
}
}




//Convert odd numbers in an array

let sum_of_odd=()=>{
let arr = [1,2,3,4,5], sum=0;
for(let i=0 ; i<arr.length ; i++)
{
    if(arr[i]%2!==0)
    {
        sum+=arr[i];
    }
}
return sum;
};
console.log(sum_of_odd());




//Convert all the strings to title caps in a string array

let capital=()=>{
let str = ['abc', 'def' , 'rst', 'xyz'];
for(let i=0 ; i<str.length ; i++)
{
    let ele = str[i].toUpperCase();
    str[i]=ele;
    
}return str;
};
console.log(capital());





//sum of all numbers in an array

let arr=[1,2,3,4,5], sum=0;
let sum_of_array=(arr)=>{

for(let i=0 ; i<arr.length ; i++)
{
    sum+=arr[i];
}return sum;

};
console.log(sum_of_array(arr));






//return all the prime numbers in an array

let arr=[1,2,3,4,5,6,7,8,9,10], sum=0, result="";
let prime=(arr)=>{

for(let i=0 ; i<arr.length ; i++)
{
    if(arr[i]===2)
    {
        result+=arr[i]+" ";
    }else
    {
        for(let j=2 ; j<arr[i] ; j++)
        {
            if(arr[i]%j===0)
            {
                break;
            }else
            {
                if(j===arr[i]-1)
                {
                    result+=arr[i]+" ";
                }else
                {
                continue;
                }
            }
        }
    }

}return result.trim();
};
console.log(prime(arr));








//return all palindromes in an array

let arr=['adib','popop','nitin','syed','aca'], reverse="", result="";
let prime=(arr)=>{

for(let i=0 ; i<arr.length ; i++)
{
    let str=arr[i].split("");
    reverse="";
    for(let j=str.length-1 ; j>=0 ; j--)
    {
        reverse+=str[j];
    }
    if(reverse===arr[i])
    {
        result+=arr[i]+" ";
    }
}
   let res=result.trim();
   return res.split(" ")
};
console.log(prime(arr));
    