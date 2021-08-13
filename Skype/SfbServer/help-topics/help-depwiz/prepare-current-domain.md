---
title: 현재 도메인 준비
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: '비즈니스용 Skype 서버 2015 또는 비즈니스용 Skype 서버 사용자를 실행하는 서버를 호스트할 도메인을 준비하려면 Using Setup to Run Domain Preparation 항목에 설명된 5단계: 현재 도메인 준비를 완료해야 합니다. 단계를 완료하려면 준비하는 도메인에서 Domain Admins 그룹의 구성원으로 로그인하거나 도메인이 속하는 포리스트의 Enterprise Admins 그룹의 구성원으로 로그인해야 합니다. 도메인을 준비하려면 다음을 수행합니다.'
ms.openlocfilehash: 5c9dca22bc0c9d633521b58fdc47effc72a20b2ef9871bd7f4330ed2edd39118
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54311486"
---
# <a name="prepare-current-domain"></a>현재 도메인 준비

비즈니스용 Skype 서버 2015 또는 비즈니스용 Skype 서버 사용자를 실행하는 서버를 호스트할 도메인을 준비하려면 Using Setup to Run Domain Preparation 항목에 설명된 **5단계:** 현재 도메인 준비를 완료해야 [합니다.](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation) 단계를 완료하려면 준비하는 도메인에서 Domain Admins 그룹의 구성원으로 로그인하거나 도메인이 속하는 포리스트의 Enterprise Admins 그룹의 구성원으로 로그인해야 합니다. 도메인을 준비하려면 다음을 수행합니다.

1. 비즈니스용 Skype 서버 2015 설치 폴더 또는 미디어에서 Setup.exe 배포 마법사를 비즈니스용 Skype 서버 실행합니다.

2. **Active Directory 준비** 를 클릭한 다음 배포 상태가 확인될 때까지 기다립니다.

3. **5단계: 현재 도메인 준비** 에서 **실행** 을 클릭합니다.

4. **명령 실행** 페이지에서 **작업 상태: 완료됨** 을 찾은 다음 **로그 보기** 를 클릭합니다.

5. 작업 **열 아래에서** **도메인** 준비를 확장하고 각 작업 끝에 있는 실행 결과를 찾아 도메인 준비가 성공적으로 완료된지 확인하고 로그를 닫고 마친 을 **\<Success\>** **클릭합니다.**

> [!TIP]
> 비즈니스용 Skype 서버 배포 마법사에서 만든 로그 파일을 검토해야 하는 경우 배포 마법사를 실행한 컴퓨터에서 해당 단계를 실행한 Active Directory 도메인 서비스 사용자의 Users 디렉터리에서 로그 파일을 찾을 수 있습니다. 예를 들어 사용자가 도메인 관리자로 로그인한 경우 Contoso.net 로그 파일은 C:\Users\Administrator.Contoso\AppData\Local\Temp에 있습니다.