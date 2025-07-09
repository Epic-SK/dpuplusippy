# dpuplusippy
Dynamic Pricing for Urban Parking Lots Capstone Project

function used to calculate dynamic pricing in second model:

price=10 + 1.5 * (3 * (pw.this.occ_max - pw.this.occ_min) / pw.this.cap - 0.5 * pw.this.que + 2 * pw.this.trf + pw.this.spl + (pw.this.veh - 1.5)).num.round(1)

occ_max is occupancy max

occ_min is occupancy min

cap is capacity of lot

^ These 3 are from model 1 which is linearly related (model 2 is linearly related as well but it is slightly more complex)


que is queue length averaged for the day: longer the queue, higher the demand for a parking space, hence positive correlation

trf is traffic condition averaged for the day (low = 0, average = 1, high = 2): higher the traffic, higher the demand for a parking space, hence positive correlation

spl is special day: higher demand for a parking space on a special day, hence positive correlation

veh is vehicle type averaged for the day (cycle = 0, bike = 1, car = 2, truck = 3): smaller vehicles less likely to pay, hence if average vehicles coming in were small vehicles, average value will also be smaller, and subtracting 1.5 will reduce the parking prices.


Found distance between each lot using haversine formula and made a distance matrix to cluster the plots into groups... but could not find a way to actively use data from other streams. 


Hence abandoned model 3 midway :(
