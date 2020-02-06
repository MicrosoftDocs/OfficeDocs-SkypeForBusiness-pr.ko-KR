---
title: Office Web Apps 서버 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 새 Office Web Apps 서버 정의 마법사는 배포에 새 Office Web Apps 서버를 정의 합니다. 다음 정보를 입력 합니다.
ms.openlocfilehash: 9f0d9680e57dd55b0a4370364aff23c7f37f57a4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820720"
---
# <a name="add-office-web-apps-server"></a>Office Web Apps 서버 추가

**새 Office Web Apps 서버 정의** 마법사는 배포에 새 Office Web apps 서버를 정의 합니다. 다음 정보를 입력 합니다.

 **Office Web Apps 서버 FQDN**: Office Web apps 서버를 호스팅할 서버의 정규화 된 도메인 이름을 입력 합니다.

 **Office Web Apps server 검색 url**: Office Web apps 서버의 전체 url (uniform resource locator)을 입력 합니다.

> [!TIP]
> **Office Web Apps 서버 검색 URL** 의 기본 동작은 다음 `https://<FQDN of the Office Web Apps Server/hosting/discovery` 형식으로 OFFICE web apps 서버의 FQDN을 기반으로 URL을 만드는 것입니다. 대부분의 경우 기본 서식을 변경할 필요는 없습니다. Office Web Apps 서버와 Office Web Apps 서버 검색 URL이 달라 야 하는 경우 기본 형식을 변경 해야 할 수 있습니다. 예를 들어 Office Web Apps 서버는 주변 네트워크에 배치 되며 위치에 따라 다른 URL을 갖게 됩니다.

 **외부 네트워크 (즉, 주변/인터넷)에 배포 되는 office Web Apps 서버**: 주변 네트워크, 외부 네트워크 또는 내부 네트워크와 동일 하지 않은 기타 네트워크 영역과 같은 내부 방화벽 외부에 Office Web apps 서버가 배치 된 경우 확인란을 선택 합니다.

## <a name="see-also"></a>참고 항목

[회의 구성 요소 및 토폴로지](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
