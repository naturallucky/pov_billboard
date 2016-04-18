//
#version 3.7;

#include "colors.inc"
#include "textures.inc"
#include "glass.inc"
#include "metals.inc"
#include "golds.inc"
#include "stones.inc"
#include "woods.inc"
#include "shapes.inc"
#include "shapes2.inc"
#include "functions.inc"
#include "math.inc"
#include "transforms.inc"
#include "skies.inc"

global_settings {
	assumed_gamma 2.2
	max_trace_level 20
}

camera {
	location <-0,0,-30>
	look_at <0,0,10>
	angle 120
}

light_source { <7, 100, -100> color rgb 1}

// 空と霞

sky_sphere {
    S_Cloud4
}

#declare si = .3;
#declare s = si*3;
#declare ls = int(10/si);

#declare rpanel =
union{
	#for (i,0,ls*2-1)
		#for (j,0,ls-1)
			sphere{<i *s
				  , j *s  ,0>  
				 si
				 pigment{ color Blue}
			}
		#end
	#end
};

#declare msg = "Hello! how are you! :p"

#declare panel =
union{
	box{<-5,-2,si*3+.1><32*2,34,si*3+.11> pigment {color rgb <0,0,0>}}
intersection
//union
{
	text { ttf "arial.ttf", msg , 1, 0.0 // thickness, offset

       texture{ pigment{ color Yellow } 
              //normal { bumps 0.5  scale 0.01 }
                finish { phong 0.1 }
              } // end of texture

       translate<0,.20,0>
       scale <30,30,si*2>
       translate<-clock*((strlen(msg)+3)*15+0),0,0>
       
      } // end of text object ---------------------------------------------
	
	
	rpanel
}

	translate <-30,-15,1>
}


object{panel } 
