..  BSD LICENSE
    Copyright 2016 6WIND S.A.

    Redistribution and use in source and binary forms, with or without
    modification, are permitted provided that the following conditions
    are met:

    * Redistributions of source code must retain the above copyright
    notice, this list of conditions and the following disclaimer.
    * Redistributions in binary form must reproduce the above copyright
    notice, this list of conditions and the following disclaimer in
    the documentation and/or other materials provided with the
    distribution.
    * Neither the name of 6WIND S.A. nor the names of its
    contributors may be used to endorse or promote products derived
    from this software without specific prior written permission.

    THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
    "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
    LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
    A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
    OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
    SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
    LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
    DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
    THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
    (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
    OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

Overview of Networking Drivers
==============================

The networking drivers may be classified in two categories:

- physical for real devices
- virtual for emulated devices

Some physical devices may be shaped through a virtual layer as for
SR-IOV.
The interface seen in the virtual environment is a VF (Virtual Function).

The ethdev layer exposes an API to use the networking functions
of these devices.
The bottom half part of ethdev is implemented by the drivers.
Thus some features may not be implemented.

There are more differences between drivers regarding some internal properties,
portability or even documentation availability.
Most of these differences are summarized below.

.. _table_net_pmd_features:

.. raw:: html

   <style>
      .wy-nav-content {
         opacity: .99;
      }
      table#id1 {
         cursor: default;
         overflow: hidden;
      }
      table#id1 th, table#id1 td {
         text-align: center;
      }
      table#id1 th {
         font-size: 80%;
         white-space: pre-wrap;
         vertical-align: top;
         padding: 2px;
      }
      table#id1 th:first-child {
         vertical-align: bottom;
      }
      table#id1 td {
         font-size: 70%;
         padding: 1px;
      }
      table#id1 td:first-child {
         padding-left: 1em;
         text-align: left;
      }
      table#id1 tr:nth-child(2n-1) td {
         background-color: rgba(210, 210, 210, 0.2);
      }
      table#id1 th:not(:first-child):hover,
      table#id1 td:not(:first-child):hover {
         position: relative;
      }
      table#id1 th:not(:first-child):hover::after,
      table#id1 td:not(:first-child):hover::after {
         content: '';
         height: 6000px;
         top: -3000px;
         width: 100%;
         left: 0;
         position: absolute;
         z-index: -1;
         background-color: #ffb;
      }
      table#id1 tr:hover td {
         background-color: #ffb;
      }
   </style>

.. include:: overview_table.txt

.. Note::

   Features marked with "P" are partially supported. Refer to the appropriate
   NIC guide in the following sections for details.
