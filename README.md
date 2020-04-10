// cricket-score-board
// calculate current_run_rate to every balls and net_run_rate to every over based on given number of total_balls
// this program is going to display current_run_rate and net_run_rate based on giving number of balls 
// and aslo display the final total score

#include<stdio.h> // include header files 
int main(void) // beginning of C program 
{ 
    // declre variables 
    int total_balls; // total balls getting from user 
    int ball_count=0; // number of balls 
    int balance_ball_count=1; // total balls % 6 
    int over_count=1; // total balls / 6 
    int run_type; //type of run 
    int extra_type; // type of extra run 
    int extra_runs; // for runs which get when extra 
    int bye_runs; // for bye runs 
    int runs; // for runs 
    int score=0; // for total score 
    float current_run_rate=0.00; // for current run rate 
    float net_run_rate=0.00; // for net run rate 

    printf("Enter total amount of balls: "); // prompt for total balls 
    scanf("%d", &total_balls); // get total balls from user 
    printf("\n"); 

    // loop for calculated over 
    // calculate current run rate and net run rate 
    while(over_count<=(total_balls/6)) 
    { 
        // loop for balls in an over 
        // calculate current run rate 
        while(ball_count<6) 
        { 
            printf("Enter not_extra or Extra(1 for not_extra / others for Extra): "); 
            scanf("%d", &run_type); 
            if(run_type==1) 
            { 
                printf("How many Runs: "); 
                scanf("%d", &runs); 
                if(runs<=6 && runs!=5) 
                    score+=runs; 
                else 
                    score+=0; 
                ball_count++; 
                current_run_rate=(float)score/ball_count; 
                printf("Current Run Rate(CRR): %.2f\n\n", current_run_rate); // display current run rate 
            } 
            else 
            { 
                printf("which type of extra(1 for bye / other for not_bye): "); 
                scanf("%d", &extra_type); 
                if(extra_type==1) 
                { 
                    printf("How many Bye_runs: "); 
                    scanf("%d", &bye_runs); 
                    score+=bye_runs; 
                    ball_count++; 
                    current_run_rate=(float)score/ball_count; 
                    printf("Current Run Rate(CRR): %.2f\n\n", current_run_rate); 
                } 
                else 
                { 
                    printf("How many more_runs they got with extra: "); 
                    scanf("%d", &extra_runs); 
                    score+=1; 
                    score+=extra_runs; 
                    if(ball_count != 0) 
                    { 
                        current_run_rate=(float)score/ball_count; 
                        printf("Current Run Rate(CRR): %.2f\n\n", current_run_rate); 
                    } 
                    else if(ball_count == 0) 
                    { 
                        current_run_rate=(float)score/1; 
                        printf("Current Run Rate(CRR): %.2f\n\n", current_run_rate); 
                    }   
                    ball_count+=0; 
                } 
            } 
        } 
        net_run_rate=(float)score/over_count; 
        printf("Net Run Rate(NRR): %.2f\n\n\n", net_run_rate); // display net run rate 
        over_count++; 
    } 
    
    // loop for calculated balance ball 
    // calculate current run rate 
    while(balance_ball_count<=total_balls%6) 
    { 
        printf("Enter not_extra or Extra(1 for not_extra / others for Extra): "); 
        scanf("%d", &run_type); 
        if(run_type==1) 
        { 
            printf("How many Runs: "); 
            scanf("%d", &runs); 
            if(runs<=6 && runs!=5) 
                score+=runs; 
            else 
                score+=0; 
            ball_count++; 
            current_run_rate=(float)score/ball_count; 
            printf("Current Run Rate(CRR): %.2f\n\n", current_run_rate); // display current run rate 
            balance_ball_count++; 
        } 
        else 
        { 
            printf("which type of extra(1 for bye / other for not_bye): "); 
            scanf("%d", &extra_type); 
            if(extra_type==1) 
            { 
                printf("How many Bye_runs: "); 
                scanf("%d", &bye_runs); 
                score+=bye_runs; 
                ball_count++; 
                current_run_rate=(float)score/ball_count; 
                printf("Current Run Rate(CRR): %.2f\n\n", current_run_rate); 
                balance_ball_count++; 
            } 
            else 
            { 
                printf("How many more_runs they got with extra: "); 
                scanf("%d", &extra_runs); 
                score+=1; 
                score+=extra_runs; 
   if(ball_count != 0) 
                    { 
                        current_run_rate=(float)score/ball_count; 
                        printf("Current Run Rate(CRR): %.2f\n\n", current_run_rate); 
                    } 
                    else if(ball_count == 0) 
                    { 
                        current_run_rate=(float)score/1; 
                        printf("Current Run Rate(CRR): %.2f\n\n", current_run_rate); 
        }                 
                ball_count+=0; 
                balance_ball_count+=0; 
            } 
        }     
    } 
  
    printf("Total Score: %d", score); // display total score 
     
    return 0; // end of the program 
} 
