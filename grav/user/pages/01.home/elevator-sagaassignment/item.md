---
title: 'Elevator SagaAssignment'
---

MOVER LAS PERSONAS DEL ASCENSOR:


## NIVEL 1.-


{

    init: function(elevators, floors) {    
    
         var elevator = elevators[0]; 
         
            elevator.on("idle", function() {
            elevator.goToFloor(0);
            elevator.goToFloor(1);
            elevator.goToFloor(2);
           
        });
    },
    update: function(dt, elevators, floors) {
        // We normally don't need to do anything here
    }
}

## NIVEL 2.-


{
   
   init: function(elevators, floors) {
    
        var elevator = elevators[0];

             elevator.on("idle", function() {
             elevator.goToFloor(0);
            elevator.goToFloor(1);
            elevator.goToFloor(2);
            elevator.goToFloor(3);
            elevator.goToFloor(4);
            elevator.goToFloor(3);
            elevator.goToFloor(2);
            elevator.goToFloor(1);
           
        });
    },
    update: function(dt, elevators, floors) {
        // We normally don't need to do anything here
    }
}

## NIVEL 3.-

{
    init: function(elevators, floors) {
        var elevator = elevators[0]; // Let's use the first elevator

        // Whenever the elevator is idle (has no more queued destinations) ...
        elevator.on("idle", function() {
            // let's go to all the floors (or did we forget one?)
            elevator.goToFloor(0);
            elevator.goToFloor(1);
            elevator.goToFloor(2);
            elevator.goToFloor(3);
            elevator.goToFloor(4);
            elevator.goToFloor(3);
            elevator.goToFloor(2);
            elevator.goToFloor(1);
           
        });
    },
    update: function(dt, elevators, floors) {
        // We normally don't need to do anything here
    }
}


## NIVEL 4.-


{
	    init: function(elevators, floors) {
	        
	        function initElevator(elevator) {
	            elevator.on("idle", function() {});
	            elevator.on("floor_button_pressed", function(floorNum) {
	                elevator.goToFloor(floorNum, true);
	            });
	            elevator.on("passing_floor", function(floorNum, direction) {
	                var stopAtFloor = false;
	                elevator.destinationQueue = elevator.destinationQueue.filter(function (n, i) {
	                    if (n == floorNum) { 
	                        stopAtFloor = true;
	                    }
	                    return n != floorNum;
	                });
	                if (stopAtFloor) {
	                    elevator.checkDestinationQueue();
	                    elevator.goToFloor(floorNum, true);                
	                }
	            });
	        };
	        
	        function findNearestElevator(floor) {
	            var possibilities = elevators
	                .map(function (e) { 
	                    return { 
	                        elevator: e, 
	                        distance: e.destinationQueue.length == 0 ? -1 : Math.abs(floor.floorNum() - e.currentFloor()),
	                    }; 
	                });
	            possibilities.sort(function (left, right) {
	                return left.distance - right.distance;
	            });
	            return possibilities[0].elevator;
	        };
	        
	        function initFloor(floor) {
	            floor.on("up_button_pressed", function() {
	                // Maybe tell an elevator to go to this floor?
	                findNearestElevator(floor).goToFloor(floor.floorNum());
	            });
	            floor.on("down_button_pressed", function() {
	                // Maybe tell an elevator to go to this floor?
	                findNearestElevator(floor).goToFloor(floor.floorNum());
	            });
	        };
	        
	        elevators.forEach(initElevator);
	        floors.forEach(initFloor);
	    },
	    update: function(dt, elevators, floors) {
	        // We normally don't need to do anything here
	    }
	}


## NIVEL 5.-


{
	    init: function(elevators, floors) {
	        
	        function initElevator(elevator) {
	            elevator.on("idle", function() {});
	            elevator.on("floor_button_pressed", function(floorNum) {
	                elevator.goToFloor(floorNum);
	            });
	            elevator.on("passing_floor", function(floorNum, direction) {
	                var stopAtFloor = false;
	                elevator.destinationQueue = elevator.destinationQueue.filter(function (n) {
	                    if (n == floorNum) { 
	                        stopAtFloor = true;
	                    }
	                    return n != floorNum;
	                });
	                if (stopAtFloor) {
	                    elevator.checkDestinationQueue();
	                    elevator.goToFloor(floorNum, true);
	                }
	            });
	        };
	        
	        function findNearestElevator(floor) {
	            var possibilities = elevators
	                .map(function (e) { 
	                    return { 
	                        elevator: e, 
	                        score: e.loadFactor() 
	                            + e.destinationQueue.length 
	                            + (Math.abs(floor.floorNum() - e.currentFloor()) / floors.length)
	                        ,
	                    }; 
	                });
	            possibilities.sort(function (left, right) {
	                return left.score - right.score;
	            });
	            return possibilities[0].elevator;
	        };
	        
	        function initFloor(floor) {
	            floor.on("up_button_pressed", function() {
	                // Maybe tell an elevator to go to this floor?
	                findNearestElevator(floor).goToFloor(floor.floorNum());
	            });
	            floor.on("down_button_pressed", function() {
	                // Maybe tell an elevator to go to this floor?
	                findNearestElevator(floor).goToFloor(floor.floorNum());
	            });
	        };
	        
	        elevators.forEach(initElevator);
	        floors.forEach(initFloor);
	    },
	    update: function(dt, elevators, floors) {
	        // We normally don't need to do anything here
	    }
	}


## NIVEL 6.-


{
	    init: function(elevators, floors) {
	        
	        function initElevator(elevator) {
	            elevator.on("idle", function() {});
	            elevator.on("floor_button_pressed", function(floorNum) {
	                elevator.goToFloor(floorNum);
	            });
	            elevator.on("passing_floor", function(floorNum, direction) {
	                var stopAtFloor = false;
	                elevator.destinationQueue = elevator.destinationQueue.filter(function (n) {
	                    if (n == floorNum) { 
	                        stopAtFloor = true;
	                    }
	                    return n != floorNum;
	                });
	                if (stopAtFloor) {
	                    elevator.checkDestinationQueue();
	                    elevator.goToFloor(floorNum, true);
	                }
	            });
	        };
	        
	        function findNearestElevator(floor) {
	            var possibilities = elevators
	                .map(function (e) { 
	                    return { 
	                        elevator: e, 
	                        score: e.loadFactor() 
	                            + e.destinationQueue.length 
	                            + (Math.abs(floor.floorNum() - e.currentFloor()) / floors.length)
	                        ,
	                    }; 
	                });
	            possibilities.sort(function (left, right) {
	                return left.score - right.score;
	            });
	            return possibilities[0].elevator;
	        };
	        
	        function initFloor(floor) {
	            floor.on("up_button_pressed", function() {
	                // Maybe tell an elevator to go to this floor?
	                findNearestElevator(floor).goToFloor(floor.floorNum());
	            });
	            floor.on("down_button_pressed", function() {
	                // Maybe tell an elevator to go to this floor?
	                findNearestElevator(floor).goToFloor(floor.floorNum());
	            });
	        };
	        
	        elevators.forEach(initElevator);
	        floors.forEach(initFloor);
	    },
	    update: function(dt, elevators, floors) {
	        // We normally don't need to do anything here
	    }
	}


## NIVEL 7.-


{
    init: function(elevators, floors) {
        var elevator = elevators[0]; // Let's use the first elevator
        var elevator2 = elevators[1];
        var elevator3 = elevators[2];
        // Whenever the elevator is idle (has no more queued destinations) ...
        elevator.on("idle", function() {
            // let's go to all the floors (or did we forget one?)
            elevator.goToFloor(0);
            elevator.goToFloor(1);
            elevator.goToFloor(0);
            elevator.goToFloor(2);
            elevator2.goToFloor(2);
            elevator2.goToFloor(0);
            elevator2.goToFloor(1);
            elevator2.goToFloor(0);
            elevator3.goToFloor(0);
            elevator3.goToFloor(1);
            elevator3.goToFloor(2);
            elevator3.goToFloor(1);
            elevator3.goToFloor(0);

        });
    },
        update: function(dt, elevators, floors) {
            // We normally don't need to do anything here
        }
}


## NIVEL 8.-


{
	    init: function(elevators, floors) {
	        
	        function initElevator(elevator) {
	            elevator.on("idle", function() {});
	            elevator.on("floor_button_pressed", function(floorNum) {
	                elevator.goToFloor(floorNum, true);
	            });
	            elevator.on("passing_floor", function(floorNum, direction) {
	                var stopAtFloor = false;
	                elevator.destinationQueue = elevator.destinationQueue.filter(function (n, i) {
	                    if (n == floorNum) { 
	                        stopAtFloor = true;
	                    }
	                    return n != floorNum;
	                });
	                if (stopAtFloor) {
	                    elevator.checkDestinationQueue();
	                    elevator.goToFloor(floorNum, true);                
	                }
	            });
	        };
	        
	        function findNearestElevator(floor) {
	            var possibilities = elevators
	                .map(function (e) { 
	                    return { 
	                        elevator: e, 
	                        distance: e.destinationQueue.length == 0 ? -1 : Math.abs(floor.floorNum() - e.currentFloor()),
	                    }; 
	                });
	            possibilities.sort(function (left, right) {
	                return left.distance - right.distance;
	            });
	            return possibilities[0].elevator;
	        };
	        
	        function initFloor(floor) {
	            floor.on("up_button_pressed", function() {
	                // Maybe tell an elevator to go to this floor?
	                findNearestElevator(floor).goToFloor(floor.floorNum());
	            });
	            floor.on("down_button_pressed", function() {
	                // Maybe tell an elevator to go to this floor?
	                findNearestElevator(floor).goToFloor(floor.floorNum());
	            });
	        };
	        
	        elevators.forEach(initElevator);
	        floors.forEach(initFloor);
	    },
	    update: function(dt, elevators, floors) {
	        // We normally don't need to do anything here
	    }
	}


## NIVEL 9.-


{
    init: function(elevators, floors) {

        function initElevator(elevator) {
            elevator.on("idle", function() {});
            elevator.on("floor_button_pressed", function(floorNum) {
                elevator.goToFloor(floorNum, true);
            });
            elevator.on("passing_floor", function(floorNum, direction) {
                var stopAtFloor = false;
                elevator.destinationQueue = elevator.destinationQueue.filter(function (n, i) {
                    if (n == floorNum) { 
                        stopAtFloor = true;
                    }
                    return n != floorNum;
                });
                if (stopAtFloor) {
                    elevator.checkDestinationQueue();
                    elevator.goToFloor(floorNum, true);                
                }
            });
        };

        function findNearestElevator(floor) {
            var possibilities = elevators
            .map(function (e) { 
                return { 
                    elevator: e, 
                    distance: e.destinationQueue.length == 0 ? -1 : Math.abs(floor.floorNum() - e.currentFloor()),
                }; 
            });
            possibilities.sort(function (left, right) {
                return left.distance - right.distance;
            });
            return possibilities[0].elevator;
        };

        function initFloor(floor) {
            floor.on("up_button_pressed", function() {
                // Maybe tell an elevator to go to this floor?
                findNearestElevator(floor).goToFloor(floor.floorNum());
            });
            floor.on("down_button_pressed", function() {
                // Maybe tell an elevator to go to this floor?
                findNearestElevator(floor).goToFloor(floor.floorNum());
            });
        };

        elevators.forEach(initElevator);
        floors.forEach(initFloor);
    },
        update: function(dt, elevators, floors) {
            // We normally don't need to do anything here
        }
}



