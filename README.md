
#include <iostream>	
#include <cstdlib>	


using namespace std;	

int main()	
{	
    int random,wrong_answers=0,right_answers=0; //random carry a random number to refer to random word //target is for print true or wrong one time.	
    char check_char,playing_again;	
    bool target=false;	
   string s[7]={"cat","park","dog","flower","hello","girl","doll"};	
   while(true){	
    random=rand()%7;	
     while(wrong_answers<5){ //this loop is to stop the game if the user entered wrong answers five times.	
            cout<<"The word contains"<<" "<<s[random].size()<<" "<<"letters"<<endl;	
        cin>>check_char;	
   for(int i=0;i<s[random].size();i++){ // this loop for check every single character in the word.	
        if(check_char==s[random][i]){	
            cout<<"you entered "<<check_char<<" which is true"<<endl;	
            right_answers++;	
            target=true;	
            break;	
        }	
         }	

         if(target==false){	
            cout<<"you entered "<<check_char<<" which is wrong"<<endl;	
            wrong_answers++;	
        }	
        target=false;	

        if(wrong_answers==5){	
             cout<<"you lost!"<<endl;	
                break;}	
        else if(right_answers==s[random].size()){cout<<"you won!"<<endl; break;}	


   }	

  cout<<"if you want to play again enter Y if not enter N"<<endl;  /* from here till the end is for allow to the user to play again*/	
     cin>>playing_again;	
     if(playing_again=='Y'||playing_again=='y') {	
       right_answers=0;	
       wrong_answers=0;	
        continue;	
     }	
     if(playing_again=='n'||playing_again=='N'){ break;}	


   }	


    return 0;	
}
 
