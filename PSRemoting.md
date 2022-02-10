
# PS REMOTING 
==================

1. It is a feature in PowerShell that let admins securely run commands on remote machines.

2. It runs via Windows Remote Management (WinRM) service.

3. It uses Web Services for Management (WS-MAN) protocol to make secure,authenticated and encrypted connections
   between computers.

4. WS-MAN is an open standard for exchanging management data securely.

==================================================================================================================================================================

# HOW PS REMOTING WORKS ?
========================
						http 5985 / https 5986
       ____________ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ ____________
       |	  |   									    |          |								
       |PowerShell|                      						    |PowerShell|
       |____>>____|_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _|____>>____|
            /\											 /\
					   Encrypted connection (256 bit Key)
	   PC1									                PC2

      __________________________________________________________________________________________________
      | 01                    | 02                      | 03                    | 04                   |  
      |                       |                         |                       |		       |	
      |  Local PowerShell     | Identity confirmed.     | Command typed on the  | The remote system    |
      | session authenticates | Privelges granted based | local system are sent | EXECUTES the commands|
      | against remote client.| on local group          | to a remote computer  | locally and sends the| 
      | 	              | membership.             | and executed locally  | results back to the  |
      |  - Enter-PSSession    | PS Session on remote    | on the Remote         | local system         |
      |  - Invoke-Command     | system via WS-MAN /     | System.               |                      |
      |  - Any Cim cmdlets    | WinRM                   |                       |                      |
      |_______________________|_________________________|_______________________|______________________|
     <-------------------------------------------------------------------------------------------------->





==================================================================================================================================================================
  
