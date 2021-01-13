---
title: 인증서 가져오기(소개)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
ROBOTS: NOINDEX, NOFOLLOW
description: 인증서를 가져오려면 인증서 파일 경로를 입력해야 합니다. 인증서 파일 선택 텍스트 상자에 전체 경로와 파일 이름을 입력하거나 찾아보기 단추를 클릭하고 경로 위치와 파일 이름(일반적으로 .p7b, .pfx 또는 .cer 파일)을 탐색할 수 있습니다.
ms.openlocfilehash: ec0eb1593c628e44fcbe5cfb8d47a381b9281406
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837108"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="2445b-104">인증서 가져오기(소개)</span><span class="sxs-lookup"><span data-stu-id="2445b-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="2445b-p102">인증서를 가져오려면 인증서 파일 경로를 입력해야 합니다. **인증서 파일 선택** 텍스트 상자에 전체 경로와 파일 이름을 입력하거나 **찾아보기** 단추를 클릭하고 경로 위치와 파일 이름(일반적으로 .p7b, .pfx 또는 .cer 파일)을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2445b-p102">To import a certificate, you must provide a path to the certificate file. In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="2445b-107">인증서에 개인 키가 포함되어 있는 경우 인증서 파일에 인증서의 개인 키가 포함된 **확인란을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="2445b-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="2445b-108">이 확인란을 선택하면 **암호** 텍스트를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2445b-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="2445b-109">인증서에 개인 키가 연결되어 있는 경우 인증서가 만들어질 때 일반적으로 암호가 개인 키에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="2445b-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="2445b-110">개인 키에 대한 암호를 입력하면 인증서 및 개인 키를 인증서 저장소로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2445b-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="2445b-111">인증서 파일 경로에 대한 정보를 입력하고 필요한 경우 선택적으로 개인 키 암호를 입력한 경우 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2445b-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2445b-112">개인 키에 대한 암호를 모르면 가져오기가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="2445b-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

