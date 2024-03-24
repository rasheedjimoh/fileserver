# File Server for Centralised file storage and sharing with Ransomware protection

## Introduction
I am pleased to guide you through the process of installing and configuring a file server for centralized file storage and sharing. This is a crucial step in streamlining your organization's data management and ensuring seamless collaboration among team members.

## Why We Need It

In today's interconnected digital landscape, the need for centralized file storage and sharing solutions is paramount. A file server serves as the cornerstone of efficient data management within organizations, providing a secure and accessible repository for critical files and documents. By centralizing file storage, businesses can streamline collaboration among team members, facilitate seamless access to resources, and ensure data consistency across the organization.

Furthermore, the rising threat of ransomware attacks underscores the importance of implementing robust security measures to safeguard sensitive data. Ransomware poses a significant risk to organizational integrity, often resulting in data loss, financial implications, and reputational damage. Hence, integrating ransomware protection mechanisms into file server infrastructure becomes imperative to mitigate these threats effectively.

In summary, the deployment of a centralized file server with ransomware protection is essential for maintaining data security, fostering collaboration, and safeguarding organizational assets in today's dynamic digital landscape.

## Installing and Configuring the File Server

1. Add the necessary roles and features to your server. To do this, go to Server Manager, click on "Add roles and features," and select "File Server" and "File Server Resource Manager" to protect against ransomware.
2. Go to Tools > Computer Management > Disk Management. Allocate a 100GB disk as the file server disk and bring it online by initialization.
3. Now, back in Server Manager, create a new share. Enable access-based enumeration and disable share caching for added security.
4. When setting permissions, disable inheritance and convert permissions. Remove any users with special permissions and add permission to allow "domain users" to access the folder.

## Mapped Network Drive

Set up a mapped network drive on client machines to easily access the shared folder on the file server.

----

![share-drive](https://github.com/rasheedjimoh/fileserver/assets/157264080/d774dc31-bf8a-43c0-b254-cc1552538f96)

----

![share-mapped](https://github.com/rasheedjimoh/fileserver/assets/157264080/51b6cacc-9820-4f80-848c-a10f993961d4)

-----

![share-working](https://github.com/rasheedjimoh/fileserver/assets/157264080/0fbfe049-3615-4002-a91b-285c7e71f391)

----

## Ransomware Protection

----

![before-script](https://github.com/rasheedjimoh/fileserver/assets/157264080/84a2022b-580f-43d9-9c02-b6f6dc417955)

---

![after-script](https://github.com/rasheedjimoh/fileserver/assets/157264080/82dfdb60-6de7-4cb9-9560-69fa184c144b)

----

For ransomware protection, navigate to Tools > File Server Resource Manager > File Screening Management. Use a PowerShell script to implement cryptolocker protection.

----

![ransom-protection](https://github.com/rasheedjimoh/fileserver/assets/157264080/4afff773-f071-4456-9725-5ad93dd1cfd5)

----

![ransom-protection-0](https://github.com/rasheedjimoh/fileserver/assets/157264080/486c331c-4f6f-4ef5-b1c6-785fbadeaaa8)

----

![ransom-protection-1](https://github.com/rasheedjimoh/fileserver/assets/157264080/ee4da14d-0b81-4d14-9632-88d7ec8a4909)

----

![ransom-protection-2](https://github.com/rasheedjimoh/fileserver/assets/157264080/7ca2ab39-47b9-49cb-9e86-c48ec410f939)

----

Schedule the script to run daily at midnight using Task Scheduler with the following settings:

- Action: Start a program
- Program/script: C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
- Add arguments: -windowstyle hidden C:\Scripts\Ransomeware_Protection.ps1
- Configure for: Windows Server 2019
- Run with the highest privilege
- Hide while running

## Testing and Verification

Test the setup by deleting all settings installed earlier and then running the script.

![ransom-poc](https://github.com/rasheedjimoh/fileserver/assets/157264080/65e74356-e594-4e9f-bd53-0413fdc7612b)

---

![ransom-poc1](https://github.com/rasheedjimoh/fileserver/assets/157264080/8b49ec7f-e99b-4a32-b9b9-184d6e11369d)

---

![ransom-poc2](https://github.com/rasheedjimoh/fileserver/assets/157264080/04e219f2-e820-4f52-b92d-a2b3dad7ab26)

----

Congratulations, your infrastructure is now resilient against ransomware attacks.

By following these steps and implementing ransomware protection measures, you've strengthened your organization's data security and ensured the integrity of your file storage and sharing infrastructure.

## Conclusion

In conclusion, the establishment of a centralized file server, fortified with robust ransomware protection measures, marks a significant stride towards enhancing organizational data security and facilitating seamless collaboration. By diligently following the outlined installation and configuration steps, along with implementing stringent ransomware protection protocols, your infrastructure now stands resilient against malicious attacks. With these measures in place, you've not only fortified your file storage and sharing infrastructure but also safeguarded the integrity of your organization's valuable data assets. Stay vigilant, stay secure!

