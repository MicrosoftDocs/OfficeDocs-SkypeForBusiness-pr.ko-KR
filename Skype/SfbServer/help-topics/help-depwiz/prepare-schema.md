---
title: 스키마 준비
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: Active Directory 도메인 서비스에 대한 schema를 준비하려면 배포 마법사에서 비즈니스용 Skype 서버 단계를 실행합니다. 실행을 클릭하여 스키마 준비를 시작합니다. Prepare Schema step reads the supplied schema definition files in the /Program Files/Microsoft Lync Server 2013/Deployment/Setup directory that the Deployment Wizard is running on. 이러한 파일은 Support/Schema 디렉터리의 설치 미디어에서도 사용할 수 있습니다. 스키마 준비 단계에서 스키마를 확장하고 프로세스의 상태를 보고합니다. 또한 프로세스가 완료되면 알려 줍니다. 요약 화면에서 프로세스 로그를 볼 수 있습니다. 로그를 검토하여 준비가 완료 및 성공되었는지 확인합니다.
ms.openlocfilehash: 162937b56a4acc91c3fef70712feb713547cd2e2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62402262"
---
# <a name="prepare-schema"></a>스키마 준비
 
Active Directory 도메인 서비스에 대한 schema를 준비하려면 배포 마법사에서 비즈니스용 Skype 서버 단계를 실행합니다. **실행** 을 클릭하여 스키마 준비를 시작합니다. Prepare Schema step reads the supplied schema definition files in the \Program Files\Microsoft Lync Server 2013\Deployment\Setup directory that the Deployment Wizard is running on. 이러한 파일은 \Support\Schema 디렉터리의 설치 미디어에서도 제공됩니다. 스키마 준비 단계에서 스키마를 확장하고 프로세스의 상태를 보고합니다. 또한 프로세스가 완료되면 알려 줍니다. 요약 화면에서 프로세스 로그를 볼 수 있습니다. 로그를 검토하여 준비가 완료 및 성공되었는지 확인합니다.
  
> [!IMPORTANT]
> 스키마를 확장하려면 Schema Admins 그룹 및 Enterprise Admins 그룹의 구성원으로 도메인에 로그인해야 합니다. 
  
2015 서버, 서비스 및 사용자 개체를 지원하도록 Active Directory 도메인 서비스 비즈니스용 Skype 서버 클래스 및 특성이 추가되었습니다. 스키마를 확장하기 전에 스키마 마스터 역할이 보관된 도메인 컨트롤러의 시스템 상태 백업을 수행해야 합니다. Windows Server 2008 R2 SP1의 백업 프로세스에 대한 자세한 내용은 을(를) 참조합니다[https://go.microsoft.com/fwlink/p/?linkId=207198](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee849849(v=ws.10)). Windows Server 2003 및 Windows Server 2003 R2의 경우 을 참조합니다[https://go.microsoft.com/fwlink/p/?linkId=207199](/previous-versions/windows/it-pro/windows-server-2003/cc787254(v=ws.10)).
  
> [!CAUTION]
> 스키마 확장은 되돌릴 수 없습니다. 가능한 모든 작업을 통해 실패한 스키마 확장의 잠재적 영향을 제한해야 하며, 스키마가 정상적으로 확장되도록 해야 합니다. 이 작업은 서버에서 통신 장애 또는 기타 오류가 발생할 경우 특히 중요합니다. 이 경우 Schema 마스터 도메인 컨트롤러의 백업과 Active Directory의 전체 백업을 수행해야 합니다. 
  
Schema 마스터 도메인 컨트롤러의 백업 및 Active Directory의 전체 백업을 수행하려면
  
1. 네트워크에서 스키마 마스터 역할이 보관된 도메인 컨트롤러의 연결을 끊습니다.
    
2. 스키마 마스터가 보관된 도메인 컨트롤러의 시스템 상태 백업을 수행합니다.
    
3. 스키마를 확장합니다.
    
4. 스키마 확장이 성공하면 도메인 컨트롤러를 네트워크에 다시 연결하고 복제가 활성 상태이고 작동 중인지 확인합니다.
    
5. 가능성은 낮지만의 경우 앞에서 수행한 시스템 상태 백업을 사용하여 도메인 컨트롤러 및 Active Directory의 시스템 상태를 복원합니다.
    
> [!NOTE]
> 비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토해야 하는 경우 배포 마법사를 실행한 컴퓨터에서 해당 단계를 실행한 Active Directory 사용자의 Users 디렉터리에서 파일을 찾을 수 있습니다. 예를 들어 사용자가 도메인 관리자로 로그인한 Contoso.net 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp에 있습니다. 
