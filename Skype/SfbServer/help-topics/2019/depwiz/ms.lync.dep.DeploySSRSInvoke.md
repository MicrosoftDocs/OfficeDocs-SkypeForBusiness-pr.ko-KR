---
title: SQL Server Reporting Services(호출)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Microsoft SQL Server 2008 R2 또는 Microsoft SQL Server 2012 보고서 서비스에 모니터링 서버를 배포 하는 데 필요한 정보를 제공 하면 페이지 실행 명령이 다음을 설치 하기 위해 실행 되는 명령의 요약을 표시 합니다. SQL Server Reporting Services에 대 한 보고서입니다.
ms.openlocfilehash: 30e97757c8ad66df9f706b6bf74549e8f1eec65f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794677"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="65471-103">SQL Server Reporting Services(호출)</span><span class="sxs-lookup"><span data-stu-id="65471-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="65471-104">Microsoft SQL Server 보고서 서비스에 모니터링 서버 보고서를 배포 하는 데 필요한 정보를 제공 하면 페이지 실행 명령이 SQL Server Reporting에 보고서를 설치 하기 위해 실행 되는 명령의 요약을 표시 합니다. 서비스도.</span><span class="sxs-lookup"><span data-stu-id="65471-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="65471-p101">명령 요약을 검토하고 명령에서 표시된 오류나 경고 메시지가 있는지 확인합니다. 로그 파일이 생성된 경우 요약 창의 드롭다운 목록에서 로그 파일을 선택하고 **로그 보기**를 클릭하여 로그 파일을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="65471-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="65471-107">Reporting Services 보고서를 성공적으로 배포 하 고 배포 완료 후에 보고서에 액세스 하려면 TCP/IP 포트 80 (필요에 따라 SSL에 대 한 TCP 포트 443 (Reporting Services에 인증서를 할당 하는 경우)이 Windows 방화벽에서 SQL Server에 고급 보안이 설정 된 상태로 열려 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65471-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="65471-108">자세한 내용은 Microsoft SQL Server 2008 R2에 대 한 [SQL Server 액세스를 허용 하도록 Windows 방화벽 구성을](https://go.microsoft.com/fwlink/p/?linkId=218031) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="65471-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](https://go.microsoft.com/fwlink/p/?linkId=218031) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="65471-109">요약을 검토 한 후 **마침을** 클릭 하 여 SQL Server Reporting Services에 대 한 보고서 설치를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="65471-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
  

