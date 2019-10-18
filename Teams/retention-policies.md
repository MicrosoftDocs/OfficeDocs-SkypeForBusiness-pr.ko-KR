---
title: Microsoft 팀의 보존 정책
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: prvijay
description: 보존 정책 및 팀에서 관리 하는 방법에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5e78e5837aa0e42f268b50bff47dab6aae71d5d2
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569954"
---
# <a name="retention-policies-in-microsoft-teams"></a>Microsoft 팀의 보존 정책

팀 대화는 영구적 이며 기본적으로 영구적으로 유지 됩니다. 보존 정책 도입으로 관리자는 팀 채팅 및 채널 메시지에 대 한 보안 & 준수 센터에서 보존 정책 (유지 및 삭제)을 구성할 수 있습니다. 이는 특정 기간이 지난 후에 조직이 책임으로 간주 되는 경우 특정 기간에 대 한 준수 (즉, 유지 정책)에 대 한 데이터를 보유 하거나 데이터 제거 (즉, 삭제 정책) 할 수 있습니다. 팀 보존 정책 데이터를 삭제 하면 팀 서비스의 모든 영구 데이터 저장소 위치에서 제거 됩니다. 

팀 보존 정책을 관리 하려면 **데이터 관리** > **보존**의 Office 365 보안 & 준수 센터에서 설정 및 cmdlet을 사용 합니다.

팀 보존 정책은 다음을 지원 합니다. 
    
- 보존: 지정 된 기간 동안 팀 데이터를 유지 한 다음 아무 작업도 수행 하지 않습니다.
- 보존 및 삭제: 지정 된 기간 동안 팀 데이터를 유지 한 다음 삭제
- 삭제: 지정 된 기간이 지난 팀 데이터 삭제

팀 보존 정책은 아직 지원 되지 않습니다.

- 고급 보존 정책은 팀 채팅 및 팀 채널 메시지 위치에 적용 되지 않습니다.
- 기간을 30 일 미만으로

관리자는 팀 개인 채팅 (1:1 또는 1: 여러 채팅) 및 팀 채널 메시지에 대 한 별도의 보존 정책을 설정할 수 있습니다. 대부분의 경우 조직은 일반적으로 프로젝트 관련 대화에 대 한 채널 메시지 보다 더 많은 책임으로 개인 채팅 데이터를 고려 합니다. 보안 & 준수 센터, **데이터 관리** > **보존**에서 이러한 정책을 설정 합니다. **팀 채널 메시지** 및 **팀 채팅** 을 켠 다음이 위치에 대 한 보존 정책 정의 (아래 다이어그램에도 표시 됨) 

**팀 채널 메시지**를 설정 하는 경우이 정책이 적용 될 팀을 지정할 수 있습니다. 예를 들어 팀 X, Y 및 Z의 경우 관리자는 해당 팀을 개별적으로 선택 하 여 1 년 동안 삭제 정책을 설정 하 고 나머지 팀에 3 년 삭제 정책을 적용할 수 있습니다. 

특정 사용자를 선택 하 고 고유한 보존 정책을 적용 하 여 **팀 채팅** 에 대해 동일한 작업을 수행할 수 있습니다. 

![Exchange 및 SharePoint에 대 한 팀 데이터 워크플로 다이어그램](media/Retention-Policies.png)


> [!IMPORTANT]
> 팀 채널 메시지 위치 및 팀 채팅 위치는 Exchange Online 사서함 (사용자 및 그룹 사서함)에 저장 된 팀 대화만 해결 합니다. 모든 관련 저장소 위치, 즉 사서함, 기판 및 채팅 서비스에서 메시지가 삭제 됩니다. 
> 
> 비즈니스용 OneDrive 및 SharePoint에 저장 된 팀 파일의 보존 정책을 관리 하려면 해당 보존 정책을 사용 합니다.

디자인에 따라 팀 파일에 대 한 삭제 정책은 SharePoint Online 및 비즈니스용 OneDrive 위치를 통해 구성 됩니다. 따라서 해당 메시지가 삭제 되기 전에 정책에서 팀 채팅 또는 채널 메시지에 참조 된 파일을 삭제할 수 있습니다. 이 경우 파일은 팀 메시지에 계속 표시 되지만 파일을 클릭 하면 "파일을 찾을 수 없음" 오류가 발생 합니다 (다른 사용자가 SharePoint Online 또는 비즈니스용 OneDrive에서 파일을 수동으로 삭제 하는 경우에도이 문제가 발생 함).

Office 365의 보존 정책을 구성 하는 방법에 대 한 자세한 내용은 [보존 정책 개요](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)를 참조 하세요.
 
