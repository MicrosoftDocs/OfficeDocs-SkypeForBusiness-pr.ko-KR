---
title: Office Web Apps Server 추가
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 새 Office Web Apps 서버 정의 마법사는 배포에 새 Office Web Apps 서버를 정의 합니다. 다음 정보를 입력합니다.
ms.openlocfilehash: 9e1726ea4b536e46fdbca5ec3eddce25358cbbbb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218729"
---
# <a name="add-office-web-apps-server"></a>Office Web Apps Server 추가

**새 Office Web Apps 서버 정의** 마법사는 배포에 새 Office Web apps 서버를 정의 합니다. 다음 정보를 입력합니다.

 **Office Web Apps 서버 FQDN**: Office Web apps 서버를 호스팅할 서버의 정규화 된 도메인 이름을 입력 합니다.

 **Office Web Apps 서버 검색 url**: Office Web apps 서버의 전체 url (uniform resource locator)을 입력 합니다.

> [!TIP]
> **Office Web Apps 서버 검색 url** 의 기본 동작은 다음 형식으로 Office Web APPS 서버의 FQDN을 기반으로 하는 url을 만드는 것입니다 `https://<FQDN of the Office Web Apps Server/hosting/discovery` . 대부분의 경우에는 기본 형식을 변경할 필요가 없습니다. Office Web Apps 서버와 Office Web Apps 서버 검색 URL이 서로 다를 때 기본 형식을 변경 해야 할 수 있습니다. 예를 들어 Office Web Apps 서버는 경계 네트워크에 배치 되며 위치에 따라 다른 URL을 갖게 됩니다.

 **Office Web Apps 서버는 외부 네트워크 (즉, 경계/인터넷)에 배포 됩니다**. Office Web apps 서버가 내부 네트워크와는 다른 내부 방화벽 (예: 경계 네트워크, 외부 네트워크 또는 기타 네트워크 영역) 외부에 있는 경우에는이 확인란을 선택 합니다.

## <a name="see-also"></a>참고 항목

[회의의 구성 요소 및 토폴로지](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
