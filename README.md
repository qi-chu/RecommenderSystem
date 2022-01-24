# RecommenderSystem

Thanks for your interest in our work. Please take a moment to read through this document.

Due to data sensitiveness, we are only able to release part of the "appreciate" data, which consists of 1 million appreciates of 63,497 users on 178,788 items (i.e. projects on https://www.behance.net/). These appreciates span from Jun. 9, 2011 to Nov. 14, 2011. Note however that it is possible to obtain the complete data through the api released by Behance (see https://www.behance.net/dev). 

Files under this folder:

* Behance_appreciate_1M.gz  
Each line is a triplet in the form of (user id, item id, unix timestamp). Note that each item id is an 8-char string.

* Behance_Item_to_Owners.gz
Each line is a tuple in the form of (item id, user id) where the user is the creator (i.e. owner) of the item. Note that some items may have multiple creators, which means there might be multiple lines corresponding to a single such item.

import struct
def readImageFeatures(path):
  f = open(path, 'rb')
  while True:
    itemId = f.read(8)
    if itemId == '': break
    feature = struct.unpack('f'*4096, f.read(4*4096))
    yield itemId, feature

Instructions for running the code:
1. Uncompress the .tar.gz file
2. Make
3. Run it
