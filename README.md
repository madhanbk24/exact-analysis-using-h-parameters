// exact-analysis-using-h-parameters

#include <stdio.h>
#include <stdlib.h>
int ce()
 {
  //long int hfe ,hre,hie,hoe;
   double r1=50000,rs=1000,rl=2000,rl_dash,ro,r2=2000,rc=2000,ri_dash,ai,yo,ri,av,avs,ais,hfe=50 ,hre=0.00025,hie=1100,hoe=0.000025;
   printf("r1:");scanf("%lf",&r1);
   printf("\nr2:");scanf("%lf",&r2);
   printf("\nrl:");scanf("%lf",&rl);
   printf("\nrs:");scanf("%lf",&rs);
   printf("\nrc:");scanf("%lf",&rc);
   printf("\nhie:");scanf("%lf",&hie);
   printf("\nhre:");scanf("%lf",&hre);
   printf("\nhfe:");scanf("%lf",&hfe);
   printf("\nhoe:");scanf("%lf",&hoe);
   if(rc!=0)
       rl_dash=(rc*rl)/(rc+rl);
   if(rc==0)
      rl_dash=rl;
   ai=-(hfe)/(1+(hoe*rl_dash));      //ai
   ri=hie+(ai*rl_dash*hre);           //ri
   if(r1!=0 && ri !=0 && r2!=0)
     ri_dash=(ri*r1*r2)/((ri*r1)+(ri*r2)+(r1*r2));
   if(r1==0 || ri ==0 || r2==0)
     {
        if(r1==0)
         ri_dash=r2*ri/(r2+ri);
        if(r2==0)
           ri_dash=r1*ri/(r1+ri);
        if(r1==0 &&r2 ==0 )    //change
           ri_dash=ri;
      }
    av=(ai*rl_dash)/(ri);  //av;
    yo=hoe-(hfe*hre)/(hie+rs);   //yo
    ro=1/yo;  //ro;
    double left,right,middle;
    avs=av*(ri_dash/(ri_dash+rs));  //avs
    if(rc==0)
     {
       right =1; //change
       middle=ai;
     }
    if(rc!=0)
     {
      right=-(rc/(rc+rl)); //change
      middle=-ai;
     }
     double temp;
     temp=(rs*r1*r2)/((r1*rs)+(r1*r2)+(r2*rs));
     
     if(r1==0 || r2==0 ||rs==0)
       {
       
       	if(r1==0)
       	 	temp=(rs*r2)/(rs+r2);
		 if(r2==0)
		   temp=(r1*rs)/(r1+rs);
		 if(rs==0)
		   temp=(r1*r2)/(r1+r2);
		 if(r1==0 &&r2==0)
		   temp=rs;
	   }
	left=temp/(temp+ri);
    ais=middle*left*right;    //ais
     
    printf("\n");
    printf("AI:%lf\nRI:%lf\nAV:%lf\nAVS:%lf\nAIS:%lf\nYO:%lf\nRO:%lf",ai,ri,av,avs,ais,yo,ro);
    return 100;  
}

void cc()
{   int a;
    double r1=10000,rs=1000,rl=5000,rl_dash,ro,r2=10000,rc=0,ri_dash,ai,yo,ri,av,avs,ais,hfe=-51 ,hre=1,hie=2000,hoe=0.000025;
    label:
    printf("1.cc readings given\n2.ce readings given");
    scanf("%d",&a);
    double hic,hrc,hoc,hfc;
    if(a==1)
     { 
          printf("r1:");scanf("%lf",&r1);
          printf("\nr2:");scanf("%lf",&r2);
          printf("\nrl:");scanf("%lf",&rl);
          printf("\nrs:");scanf("%lf",&rs);
          printf("\nre:");scanf("%lf",&rc);
          printf("\nhic:");scanf("%lf",&hie);
          printf("\nhrc:");scanf("%lf",&hre);
          printf("\nhfc:");scanf("%lf",&hfe);
          printf("\nhoc:");scanf("%lf",&hoe);
        
     }
     else if(a==2)
      {
        printf("r1:");scanf("%lf",&r1);
        printf("\nr2:");scanf("%lf",&r2);
        printf("\nrl:");scanf("%lf",&rl);
        printf("\nrs:");scanf("%lf",&rs);
        printf("\nre:");scanf("%lf",&rc);
        printf("\nhie:");scanf("%lf",&hie);
        printf("\nhre:");scanf("%lf",&hre);
        printf("\nhfe:");scanf("%lf",&hfe);
        printf("\nhoe:");scanf("%lf",&hoe); 
        hre=1;
        hfe=-(1+hfe);
      }
     else goto label;
     if(rc!=0)
       rl_dash=(rc*rl)/(rc+rl);
     if(rc==0)
      rl_dash=rl;
     ai=-(hfe)/(1+(hoe*rl_dash));  //ai
     ri=hie+(ai*rl_dash*hre);           //ri
   
     if(r1!=0 && ri !=0 && r2!=0)
       ri_dash=(ri*r1*r2)/((ri*r1)+(ri*r2)+(r1*r2));
     if(r1==0 || ri ==0 || r2==0)
      {
        if(r1==0)
         ri_dash=r2*ri/(r2+ri);
        if(r2==0)
           ri_dash=r1*ri/(r1+ri);
        if(r1==0 &&r2 ==0 )
           ri_dash=ri;
      }
    av=(ai*rl_dash)/(ri);  //av;
    yo=hoe-(hfe*hre)/(hie+rs);   //yo
    ro=1/yo;  //ro;
    double left,right,middle;
    avs=av*(ri_dash/(ri_dash+rs));  //avs
    if(rc==0)
     {
       right =1;
       middle=ai;
     }
    if(rc!=0)
     {
      right=-rl/(rc+rl);
      middle=-ai;
     }
    double temp;
    temp=(rs*r1*r2)/((r1*rs)+(r1*r2)+(r2*rs));
     
    if(r1==0 || r2==0 ||rs==0)
       {
       	 if(r1==0)
       	 	temp=(rs*r2)/(rs+r2);
		 if(r2==0)
		   temp=(r1*rs)/(r1+rs);
		 if(rs==0)
		   temp=(r1*r2)/(r1+r2);
		 if(r1==0 &&r2==0)
		   temp=rs;
	   }
	left=temp/(temp+ri);
    ais=middle*left*right;       //ais
    printf("\n");
    printf("AI:%lf\nRI:%lf\nAV:%lf\nAVS:%lf\nAIS:%lf\nYO:%lf\nRO:%lf",ai,ri,av,avs,ais,yo,ro);
    
}

void cb()
 {
    int a;
    double r1=0,rs=1200,rl=1000,rl_dash,ro,r2=0,rc=0,ri_dash,ai,yo,ri,av,avs,ais,hfe= -0.98 ,hre=0.0003,hie=22,hoe=0.000005;
    double hib,hrb,hob,hfb;
    label:
    printf("1.cb readings given\n2.ce readings given");
    scanf("%d",&a);   
    if(a==1)
     { 
          printf("r1:");scanf("%lf",&r1);
          printf("\nr2:");scanf("%lf",&r2);
          printf("\nrl:");scanf("%lf",&rl);
          printf("\nrs:");scanf("%lf",&rs);
          printf("\nre:");scanf("%lf",&rc);
          printf("\nhib:");scanf("%lf",&hie);
          printf("\nhrb:");scanf("%lf",&hre);
          printf("\nhfb:");scanf("%lf",&hfe);
          printf("\nhob:");scanf("%lf",&hoe);
         
        
     }
    else if(a==2)
     {
          printf("r1:");scanf("%lf",&r1);
          printf("\nr2:");scanf("%lf",&r2);
          printf("\nrl:");scanf("%lf",&rl);
          printf("\nrs:");scanf("%lf",&rs);
          printf("\nre:");scanf("%lf",&rc);
          printf("\nhib:");scanf("%lf",&hib);
          printf("\nhrb:");scanf("%lf",&hrb);
          printf("\nhfb:");scanf("%lf",&hfb);
          printf("\nhob:");scanf("%lf",&hob); 
          hie=(hib)/(1+hfb);
          hre=((hib*hoe)/(1+hib))-hrb;
          hfe=(-hfb)/(1+hfb);
          hoe=(hob/1+hfb);
    
    }
    else goto label;
   
    if(rc!=0)
       rl_dash=(rc*rl)/(rc+rl);
    if(rc==0)
      rl_dash=rl;
    ai=-(hfe)/(1+(hoe*rl_dash));  //ai
    ri=hie+(ai*rl_dash*hre);           //ri
   
    if(r1!=0 && ri !=0 && r2!=0)
     ri_dash=(ri*r1*r2)/((ri*r1)+(ri*r2)+(r1*r2));
    if(r1==0 || ri ==0 || r2==0)
     {
        if(r1==0)
         ri_dash=r2*ri/(r2+ri);
        if(r2==0)
           ri_dash=r1*ri/(r1+ri);
        if(r1==0 &&r2 ==0 )
           ri_dash=ri;
      }
    av=(ai*rl_dash)/(ri);  //av;
    yo=hoe-(hfe*hre)/(hie+rs);   //yo
    ro=1/yo;  //ro;
    double left,right,middle;
    avs=av*(ri_dash/(ri_dash+rs));  //avs  //change
    if(rc==0)
     {
       right =1;
       middle=ai;
     }
    if(rc!=0)
     {
      right=-rc/(rc+rl);   //change
      middle=-ai;
     }
    double temp;
    temp=(rs*r1*r2)/((r1*rs)+(r1*r2)+(r2*rs));
     
    if(r1==0 || r2==0 ||rs==0)
       {
       
       	if(r1==0)
       	 	temp=(rs*r2)/(rs+r2);
		 if(r2==0)
		   temp=(r1*rs)/(r1+rs);
		 if(rs==0)
		   temp=(r1*r2)/(r1+r2);
		 if(r1==0 &&r2==0)
		  temp=rs;
	   }
	left=temp/(temp+ri);
    ais=middle*left*right;     //ais
     
    printf("\n");
    printf("AI:%lf\nRI:%lf\nAV:%lf\nAVS:%lf\nAIS:%lf\nYO:%lf\nRO:%lf",ai,ri,av,avs,ais,yo,ro);
    
 }  
 
int main()
{  int a;
   again:
   printf("1.COMMON EMITTER\n2.COMMON BASE\n3.COMMON COLLECTOR\n4. EXIT\n");
   scanf("%d",&a);
    
   switch(a)
     {
         case 1:
            ce();
            break;
         case 2:
            cb();
            break;
         case 3:
            cc();
            break;
         case 4:
        	exit(1);
        	break;
         default :
          	{
            printf("INVALID INPUT\n");
            goto again;
            }
     }
   return 0;
}
