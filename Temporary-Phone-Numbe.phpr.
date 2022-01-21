<?php

header("Content-Type: application/json; charset=UTF-8");

function Phone(){
        $ch = curl_init();
        curl_setopt($ch, CURLOPT_URL, "https://receive-smss.com");#<h4 class="number-boxes-itemm-number">+380999373708</h4>
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
        $output = curl_exec($ch);
        curl_close($ch); 
preg_match_all('/<h4 class="number-boxes-itemm-number">(.*?)<\/h4>/s',$output,$matches);
preg_match_all('/<h5 class="number-boxes-item-country number-boxess-item-country">(.*?)<\/h5>/s',$output,$matches2);
$i1 = rand(0,59);
$i2 = rand(0,59);
$i3 = rand(0,59);
$i4 = rand(0,59);
$i5 = rand(0,59);
$i6 = rand(0,59);
$i7 = rand(0,59);
$i8 = rand(0,59);
$i9 = rand(0,59);
$i0 = rand(0,59);
$h = [];
$h[] = $matches[1][$i1];
$h[] = $matches[1][$i2];
$h[] = $matches[1][$i3];
$h[] = $matches[1][$i4];
$h[] = $matches[1][$i5];
$h[] = $matches[1][$i6];
$h[] = $matches[1][$i7];
$h[] = $matches[1][$i8];
$h[] = $matches[1][$i9];
$h[] = $matches[1][$i0];
$xjson = json_encode([
    'result'=>$h,'tip'=>"How to Enter message : https://iqhost.xyz/Phone/{Your-phone-Number}"],JSON_UNESCAPED_UNICODE | JSON_PRETTY_PRINT | JSON_UNESCAPED_SLASHES);

return $xjson;
}

function Message($num){
            $ch = curl_init();
        curl_setopt($ch, CURLOPT_URL, "https://receive-smss.com/sms/$num/");#<h4 class="number-boxes-itemm-number">+380999373708</h4>
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);
        $output = curl_exec($ch);
        curl_close($ch);
  preg_match_all('/<td class="wr3pc52sel1757">(.*?)<\/td>/',$output,$matches);  

return  json_encode(['last_Message'=>$matches[1][64]]);

}



function Request(){
$return = str_replace("/apis/phone-api.php/","",$_SERVER['REQUEST_URI']);
return $return;
}

$phone = Request();
if(!preg_match('/([0-9])/',$phone)){
    echo Phone();
}elseif(preg_match('/([0-9])/',$phone)){
  echo Message(str_replace("+",null,explode("|",$phone)[0]));
}



