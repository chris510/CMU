# Redundancy and Replication

Created By: Chris Trinh
Last Edited: Jan 17, 2020 3:57 PM

- What is redundancy?
    - Duplication of components or functions of a systen to increase reliability of the system
    - e.g Backups or fail-safes; create duplicate copies of a file to store on a system incase one gets lost.
- What is the role in redundancy?
    - Helps in single pint failure of the system providing backups
- What is replication?
    - Sharing information to ensure consistency between redundant resources
- What is fault tolerance?
    - Property to enable a system to continue operating properly even if theres a failure of one or some of its components
- How is replication used in DBMS?
    - parent-child relationship where parents gets all updates and then ripples through the childs. Child then outputs a message stating it received the update successfully.