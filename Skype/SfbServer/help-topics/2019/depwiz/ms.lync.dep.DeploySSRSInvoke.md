---
title: SQL Server Reporting Services(호출)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft SQL Server 2008 R2 또는 Microsoft SQL Server 2012 Report Services에 모니터링 서버 보고서를 배포하는 데 필요한 정보를 제공하면 명령 실행 페이지에 SQL Server Reporting Services에 보고서를 설치하기 위해 실행되는 명령 요약이 표시됩니다.
ms.openlocfilehash: 17824f79ab0d710d4969d736b864912b424abaa9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109664"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="fa76f-103">SQL Server Reporting Services(호출)</span><span class="sxs-lookup"><span data-stu-id="fa76f-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="fa76f-104">Microsoft SQL Server Report Services에 모니터링 서버 보고서를 배포하는 데 필요한 정보를 제공하면 명령 실행 페이지에 SQL Server Reporting Services에 보고서를 설치하기 위해 실행된 명령 요약이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa76f-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="fa76f-p101">명령 요약을 검토하고 명령에서 표시된 오류나 경고 메시지가 있는지 확인합니다. 로그 파일이 생성된 경우 요약 창의 드롭다운 목록에서 로그 파일을 선택하고 **로그 보기** 를 클릭하여 로그 파일을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76f-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fa76f-107">Reporting Services 보고서가 배포에 성공하고 배포가 완료된 후 보고서에 액세스하려면 보고서의 고급 보안이 있는 Windows 방화벽에 TCP/IP 포트 80이 열려 SQL Server 있어야 합니다(필요한 경우 Reporting Services에 인증서를 할당하는 경우 SSL용 TCP 포트 443).</span><span class="sxs-lookup"><span data-stu-id="fa76f-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="fa76f-108">자세한 내용은 [Configure the Windows Firewall to Allow SQL Server Access](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) for Microsoft SQL Server R2을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76f-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="fa76f-109">요약을 검토한 후 마친을 **클릭하여** Reporting Services에 대한 보고서 SQL Server 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="fa76f-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
