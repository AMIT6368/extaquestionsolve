# extaquestionsolve  -- https://www.hackerrank.com/
1.There are two data tables with employee information: EMPLOYEE and EMPLOYEE UIN. Query the tables to generate a list of all employees who are less than 25 years old first in order of NAME, then of ID, both ascending. The result should include the UIN followed by the NAME.  Note: While the secondary sort is by ID, the result includes UIN but not ID

Answer: 
select a.UIN,b.NAME
from EMPLOYEE as b
JOIN EMPLOYEE_UIN as a
ON a.ID = b.ID
where b.AGE < 25
ORDER BY b.NAME, a.ID;

2. Erica and Bob participate in a friendly Hackathon that allows each one to solve one question a day out of the three offered. There will be one easy, one medium and one hard question, with points awarded based on difficulty. The winner is the one with the highest score at the end of the competition based on the following scale:
------------------------------------------------------------------------------------------------------------------
                                                Answer : javascript - nodejs

function winner(erica, bob) {

  // Write your code here
  const getScore = (str) => {
    let scoreMap = {
      E: 1,
      M: 3,
      H: 5
    }
    
    let score = 0;
    str.split("").forEach(el => {
      if(el){
        score = score + scoreMap[el];
      }
    });
    return score;
  };
   let sEri = getScore(erica);
   let sBob = getScore(bob);
  if(sEri > sBob ){
    return "Erica";
  }
  else if(sEri < sBob){
    return "Bob";
  }
  return "Tie";
}
---------------------------------------------------------------------------------------------------------------
=================================================================================================================
---------------------------------------------------------------------------------------------------------------
                                Answer 2  WITH PHP

$erica = ["H","H","E"];
$bob = ["M","M","M"];
$sumBobscore = winner($erica,$bob);
function winner($erica, $bob) {
    $sumEricascore = getScore($erica);
    $sumBobscore = getScore($bob); 
    if($sumEricascore > $sumBobscore){       
        print_r('Erica');
    }else if($sumEricascore < $sumBobscore){        
        print_r('Bob');        
    }else if($sumEricascore == $sumBobscore){    
        print_r('Tie');
    }
}

function getScore($valstring){
  $totalscorefinal = [];
  $totalscorefinal['getallscore']=0;
  foreach($valstring as $stringval){
      if($stringval=='E'){
          $totalscorefinal['getallscore'] += abs(1);
      }else if($stringval=='M'){
          $totalscorefinal['getallscore'] += abs(3);          
      }else if($stringval=='H'){
          $totalscorefinal['getallscore'] += abs(5);
      }       
  } 
  $score =  abs($totalscorefinal['getallscore']);
  return $score; 
}

----------------------------------------------------------------------------------------------------
====================================================================================================================================================
