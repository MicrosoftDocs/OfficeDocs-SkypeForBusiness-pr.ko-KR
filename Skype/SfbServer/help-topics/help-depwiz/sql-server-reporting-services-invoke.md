---
title: SQL Server Reporting Services(호출)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: Microsoft SQL Server 2008 R2 또는 Microsoft SQL Server 2012 Report Services에 모니터링 서버 보고서를 배포하는 데 필요한 정보를 제공하면 명령 실행 페이지에 SQL Server Reporting Services에 보고서를 설치하기 위해 실행되는 명령 요약이 표시됩니다.
ms.openlocfilehash: eac8b7884859c0b5b14218471054533eedb6d481
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829538"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="c0b8c-103">SQL Server Reporting Services(호출)</span><span class="sxs-lookup"><span data-stu-id="c0b8c-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="c0b8c-104">Microsoft SQL Server 2008 R2 또는 Microsoft SQL Server 2012 Report Services에 모니터링 서버 보고서를 배포하는 데 필요한 정보를 제공하면 명령 실행 페이지에 SQL Server Reporting Services에 보고서를 설치하기 위해 실행되는 명령 요약이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0b8c-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server 2008 R2, or to Microsoft SQL Server 2012 Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="c0b8c-p101">명령 요약을 검토하고 명령에서 표시된 오류나 경고 메시지가 있는지 확인합니다. 로그 파일이 생성된 경우 요약 창의 드롭다운 목록에서 로그 파일을 선택하고 **로그 보기** 를 클릭하여 로그 파일을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c0b8c-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c0b8c-107">Reporting Services 보고서를 성공적으로 배포하고 배포가 완료된 후 보고서에 액세스하려면 TCP/IP 포트 80(그리고 Reporting Services에 인증서를 할당하는 경우 SSL용 TCP 포트 443)이 보고서의 고급 보안이 있는 Windows 방화벽에 열려 있어야 SQL Server.</span><span class="sxs-lookup"><span data-stu-id="c0b8c-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="c0b8c-108">자세한 내용은 [Windows](https://go.microsoft.com/fwlink/p/?linkId=218031) 방화벽을 구성하여 SQL Server 2008 R2에 대한 Microsoft SQL Server 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="c0b8c-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](https://go.microsoft.com/fwlink/p/?linkId=218031) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="c0b8c-109">요약을 검토한 후 마친 후 **Reporting** Services에 대한 보고서 설치를 SQL Server 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c0b8c-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
  

