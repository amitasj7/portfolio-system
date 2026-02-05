axis define: 
x-axis: left to right of screen
y-axis: top to bottom of screen
z-axis: front to back of screen
origin : center of screen

w: screen width
h: screen height

di: a constant distance (take by yourself)

x1 = 0
z1 = 5*di

a = 5*di/2
c = di/2

linear velocity: v 
rotatiioin velocity: omega = v*hero  card width

# HERO  CARD ANIMATION - 05-02-2026

PRESENT : card animation is not good. problem
future update: i want to animate this card in z-x plane.

    - suppose there is a ellipse (2D shape) in z-x plane. 
        - equation of ellipse:  ((x-x1)^2)/(a^2) + ((z-z1)^2)/(c^2)= 1
    - camera position: (0, 0, 0)
    - hero card:
        - intial position: s1(0,0,-2c)
        - mid position: s2(0,0,0)
        - final position: s3(0,0,-2c)
        
        motion:
        hero card always follow ellipse path. not a straight line.

        when user scroll down then:
        first half path:
        - intially start from s1 postion with linear speed 0.
        - then increase linear speed with a accelaration (ac).
        - when it cover almost 80% path b/w s1 and s2 then decrease linear speed.
        - stop at s2 positon with linear speed 0. 
        
        now when user scroll more down the
        second half path:
            - intially start from s2 postion with linear speed 0.
            - then increase linear speed with a accelaration (ac).
            - when it cover almost 80% path b/w s2 and s3 then decrease linear speed.
            - stop at s3 positon with linear speed 0.

        rotation:
            - hero card always rotate about y-axis.
            - rotation angle = 360 degree
            - hero card rotate with omega angular velocity.


update: 
    present: 
        - when card come near to camera it's show completly back part. problem
        update: i want opposite:
            - when card come near to camera it show front part.

    present: 
        - rotation at 360 happens only 1 time.
        update:
            - take a variable: rotation_count
            - so rotation_count = 100
            - so rotation angle = 360 * rotation_count



working dir: portfolio-frontend\src\components\3d
if you need other, then you can also take


first you have understand this physics phenomena.
create a task and implement file

after take my review, we will continue



