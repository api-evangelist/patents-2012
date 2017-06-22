---

title: Architecture and method for a burst buffer using flash technology
abstract: A parallel supercomputing cluster includes compute nodes interconnected in a mesh of data links for executing an MPI job, and solid-state storage nodes each linked to a respective group of the compute nodes for receiving checkpoint data from the respective compute nodes, and magnetic disk storage linked to each of the solid-state storage nodes for asynchronous migration of the checkpoint data from the solid-state storage nodes to the magnetic disk storage. Each solid-state storage node presents a file system interface to the MPI job, and multiple MPI processes of the MPI job write the checkpoint data to a shared file in the solid-state storage in a strided fashion, and the solid-state storage node asynchronously migrates the checkpoint data from the shared file in the solid-state storage to the magnetic disk storage and writes the checkpoint data to the magnetic disk storage in a sequential fashion.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09286261&OS=09286261&RS=09286261
owner: Los Alamos National Security, LLC
number: 09286261
owner_city: Los Alamos
owner_country: US
publication_date: 20121113
---
