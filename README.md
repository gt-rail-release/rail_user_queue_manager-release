rail_user_queue_manager [![Build Status](https://api.travis-ci.org/WPI-RAIL/rail_user_queue_manager.png)](https://travis-ci.org/WPI-RAIL/rail_user_queue_manager)
=======================

#### Server Side ROS Queue Node
For full documentation, see [the ROS wiki](http://ros.org/wiki/rail_user_queue_manager).

### License
queue_manager is released with a BSD license. For full terms and conditions, see the [LICENSE](LICENSE) file.

### Authors
See the [AUTHORS.md](AUTHORS.md) file for a full list of contributors.

### Notes From Peter
Topics:
 - rms_queue - publishes for each user: user id, time left in queue (valid for non 1st user only), and time left in study (valid for 1st user only)

Services:
 - update_queue - called by the web interface when someone: loads the webpage, reloads the webpage, exist the browser, or navigates to another website

### Known Bugs
 - study time can go negative when all users leave the queue. This has never caused any inappropriate behavior though, since it only happens when everyone leaves
 - study time described in the Ros_Queue object may not be respected, and will default to 10 minute trials. It should work but I has at times not worked. At least you know it's possible.
