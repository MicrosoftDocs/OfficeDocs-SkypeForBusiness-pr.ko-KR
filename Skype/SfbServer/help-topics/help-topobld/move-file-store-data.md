---
title: 비즈니스용 Skype 서버 2015에서 새 파일 저장소로 파일 저장소 데이터를 이동 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 비즈니스용 Skype 서버 2015 배포를 위해 현재 파일 저장소로 작동 하는 파일 서버를 제거 해야 하거나, 현재 파일 저장소를 사용할 수 없도록 하는 다른 변경 작업을 수행 해야 하는 경우에는 먼저 새 공유를 만들어야 합니다. 그런 후에는 다음 단계를 수행 해야 합니다.
ms.openlocfilehash: c9bdc7ac572ecd8a71022e5a267454b795ef7cc6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215589"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에서 새 파일 저장소로 파일 저장소 데이터를 이동 합니다.

비즈니스용 Skype 서버 2015 배포를 위해 현재 파일 저장소로 작동 하는 파일 서버를 제거 해야 하거나, 현재 파일 저장소를 사용할 수 없도록 하는 다른 변경 작업을 수행 해야 하는 경우에는 먼저 새 공유를 만들어야 합니다. 그런 후에는 다음 단계를 수행 해야 합니다.

1. 제거 하려는 파일 저장소를 사용 하는 비즈니스용 Skype 서버 2015 서비스를 종료 합니다.

2. 토폴로지 작성기에서 파일 저장소를 정의 하 고 변경 내용을 게시 하 여 새 파일 저장소를 배포에서 사용할 수 있도록 합니다.

3. 데이터를 새 파일 저장소로 이동 합니다.

4. 서버 또는 서비스를 다시 시작 합니다.

5. 필요한 경우 이전 파일 공유 및 파일 폴더를 제거 합니다.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>하나의 파일 저장소에서 새 파일 저장소로 파일 저장소 데이터를 이동하려면

1. 비즈니스용 Skype 서버 2015, 관리 도구가 설치 되어 있는 된 rtcuniversersalserveradmins 또는 CsServerAdministrator 그룹의 구성원으로 컴퓨터에 로그온 합니다.

2. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.

3. 왼쪽 탐색 모음에서 **토폴로지**를 클릭하고 **상태**를 클릭합니다.

4. 제거할 파일 저장소를 사용 하는 각 디렉터 풀, 디렉터, Standard Edition server 및 프런트 엔드 풀에 대해 서버 또는 풀을 선택 하 고 **동작**을 클릭 한 후에 **모든 서비스 중지**를 클릭 합니다.

5. 토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.

6. 토폴로지 작성기 시작: **시작**, **모든 프로그램**, **비즈니스용 skype 서버 2015**을 차례로 클릭 한 다음 비즈니스용 **skype 서버 20154토폴로지 작성기**를 클릭 합니다.

7. 파일 저장소를 사용 하는 서버 또는 풀을 선택 하 고 다음을 수행 합니다.

8. 서버 또는 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

9. **속성 편집**의 **연결**아래에 있는 **파일 저장소**에서 **새로 만들기**를 클릭 합니다.

10. **새 파일 저장소 정의**의 **파일 서버 fqdn**에 파일 서버의 fqdn (정규화 된 도메인 이름)을 입력 합니다. **파일 공유**아래에서 새 파일 공유의 폴더 이름을 입력 한 다음 **확인**을 클릭 합니다.

     > [!IMPORTANT]
     > 이 단계에서는 토폴로지 작성기에서 사용할 새 파일 저장소를 정의 합니다. 각 서버에 대해 한 번만 정의 하면 됩니다. 토폴로지를 게시하기 전에 정의된 파일 서버에서 정의된 파일 공유를 만들어야 합니다. 자세한 내용은 [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx)를 참조하십시오.

11. 파일 저장소를 사용 하는 각 서버 또는 풀에 대해 다음을 수행 합니다.

12. 서버 또는 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

13. **속성 편집**의 **연결**아래에 있는 **파일 저장소**에서 새 파일 공유를 선택 하 고 **확인**을 클릭 합니다.

14. 토폴로지를 게시 하 고, 복제 상태를 확인 한 다음 필요에 따라 비즈니스용 Skype 서버 배포 마법사를 실행 합니다. 자세한 내용은 [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx)을 참조하십시오.

15. **시작**을 클릭 하 고 **실행**을 클릭 한 다음 cmd.exe를 입력 하 여 명령 프롬프트를 시작 합니다.

16. 명령줄에 다음을 입력합니다.

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > /S 스위치는 파일, 디렉터리 및 하위 디렉터리를 복사 합니다. /XF 스위치는 이름이 Meeting 인 모든 파일을 건너뜁니다. 현재 버전의 robocopy.exe에 /MT 스위치를 사용하면 다중 스레드를 사용하여 복사 속도를 크게 향상시켜 줍니다. /LOG 스위치의 경우 C:\Logfiles\log.txt 형식으로 디렉터리 경로와 로그 파일 이름을 사용 합니다. 이 스위치는 명명 된 위치에 작업의 로그 파일을 만듭니다.

17. 데이터 복사가 완료 되 면 Lync Server 제어판에서 **토폴로지**를 클릭 하 고 **상태**를 클릭 합니다.

18. 서비스를 중지 한 각 서버 또는 풀에 대해 서버 또는 풀을 선택 하 고 **동작**을 클릭 한 후에 **모든 서비스 시작**을 클릭 합니다.

19. 토폴로지에서 오래된 파일 저장소를 제거한 후 토폴로지를 게시합니다. 자세한 내용은 [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)를 참조하십시오.

20. (선택 사항) 바로 전에 제거한 파일 저장소가 포함된 컴퓨터에 로컬 Administrators 그룹 또는 도메인 관리자 그룹의 구성원으로 로그온한 후 오래된 파일 공유 및 디렉터리를 제거합니다.

## <a name="see-also"></a>참고 항목

[서버를 다른 파일 저장소에 다시 할당](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[파일 저장소 제거](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
