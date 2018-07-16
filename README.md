# WARPLab Matlab Wrapper
This is the way I like to use WARPLab with the WARPv3 board. [Checkout the WARP website for more info on WARP.](https://warpproject.org/trac)

This repo has a WARP class that handles most of the details. To use, just put in your directory. 

Initialize with:
`board = WARP(params);`

The 'params' stuct needs to contain the following:
  `params.nBoards`: Number of boards. Currently, I only use 1 board, so I haven't fully set this up for more boards.
  `params.RF_port`: "A2B" sets RF A as the TX and RF B as RX. "B2A" does the opposite.
  
  There are various settings that are set up in the class constructor. These include gain and channel settings. Set these up for your purposes then just run with it.
  
  To send something through the WARP board, simply use the transmit method.
  `rxData = board.transmit(txData)`
  
  This assumes that we are doing loopback. It'll therefore try to sync the rxData to the txData. 