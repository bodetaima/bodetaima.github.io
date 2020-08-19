---
layout: post
title:  "Moving to Fish"
date:   2020-08-19 15:00:00 +0700
categories: [linux, shell, fish]
---

Có một sự thật, dù muốn hay không, bạn vẫn sẽ phải làm việc với hệ điều hành có nhân Unix hoặc Unix-like (Linux-based) như MacOS, Ubuntu,...Chúng mạnh mẽ, ổn định, hiệu quả, có thể tùy biến một cách vạn hóa. Và chúng có Unix Shell. Dù muốn hay không, dù sớm hay muộn, bạn sẽ yêu chúng.

Trong suốt một năm trở lại đây, mình là người dùng quen thuộc với Zsh. Bất kể bộ máy chạy Unix nào mình làm việc cùng, chắc chắn nó sẽ có Zsh. Zsh có rất nhiều tính năng, đa dạng về mặt hình thức và khả năng tùy biến thì tuyệt vời. Thậm chí nó còn được cộng đồng ưu ái phát triển cho hẳn một framework ([oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh)), một plugin manager ([antigen](https://github.com/zsh-users/antigen)) và vô số plugin hay ho và hữu dụng. Thậm chí với MacOS Catalina, Apple đã sử dụng Zsh làm shell mặc định. Nhưng việc phát triển Zsh ecosystems là không đồng nhất, đôi khi gây ra sự chậm chạp và nặng nề cho Zsh, dù đã có rất nhiều cố gắng từ cộng đồng để cải thiện hệ sinh thái này.

Nhiều developer đã đưa ra những giải pháp cải thiện tốc độ cho Zsh, ví dụ như [giải pháp đẩy nhanh tốc độ pasting khi sử dụng zsh-autosuggestions](https://thienkphan.com/posts/06012019/faster-pasting-with-zsh-auto-suggestions-on.html) của một người bạn của mình. Hoàn toàn ổn và ngon lành. Nhưng với mình, mọi thứ nên được "work out-of-the-box", tiết kiệm thời gian setup hệ thống cho mỗi lần làm việc, giúp mình có thể tập trung phát triển hơn.

Vì thế, sau hơn 1 năm gắn bó, mình tới với Fish.

### Fish

Fish, "Friendly Interactive Shell", đứa em sinh sau đẻ muộn của một đại gia đình Unix Shell. Với chỉ vỏn vẹn 15 năm phát triển, Fish thực sự mới chỉ là một cậu bé tuổi mới lớn nếu so với những đàn anh như Bash, Zsh, thậm chí là bậc cha chú như sh hay csh. Nhưng sinh sau đồng nghĩa với việc, Fish có thể học hỏi và tích hợp những ưu điểm tốt nhất của những shell đi trước.

### Vậy thì Fish có gì?

#### Dễ dàng cài đặt và sử dụng

Fish có mặt trên MacOS, Windows và hầu hết các Linux/BSD distros phổ biến. Fish sẵn sàng sử dụng chỉ sau 1 câu lệnh, không cần thiết phải config hoặc cài đặt thêm plugins. Ngay cả khi bạn cần, những tác vụ này được hỗ trợ bởi những câu lệnh với cú pháp sạch sẽ, đơn giản và rõ ràng.

Nhắc tới plugins, có thể kể đến như:

#### Syntax Highlighting

Một tính năng mà không những ai cũng muốn, mà còn ai cũng cần. Bạn có thể không tin, những có tính năng này, bạn tiết kiệm được hàng ngàn phút cuộc đời. Và Fish làm nó rất tốt, "out-of-the-box".

![fish-syntax-highlighting](https://raw.githubusercontent.com/bodetaima/bodetaima.github.io/master/static/img/_posts/fish-syntax-highlighting.png)

Và nếu như bạn chưa biết, Fish hỗ trợ 24-bit true color terminal. "Out-of-the-box". Điều đó có nghĩa là, bạn có hơn 3 cái cầu vồng trong tay :D

#### Khả năng tùy biến

Fish có một framework được lấy cảm hứng từ Oh My Zsh,...Oh My Fish. [Oh My Fish](https://github.com/oh-my-fish/oh-my-fish) được phát triển trở thành một ứng dụng CLI hoàn chỉnh, cung cấp khả năng config, cài đặt plugin,... thông qua command `omf`. Hầu hết mọi thứ bạn cần và muốn làm với Fish, bạn làm với `omf`.

Ngoài ra fish cung cấp 1 web-based configuration, với command:
`$ fish_config`
Trang web config của fish sẽ "hạ cánh" ngay trên trình duyệt của bạn.

![web-config](https://raw.githubusercontent.com/bodetaima/bodetaima.github.io/master/static/img/_posts/web_config.png)

#### Inline searchable history

Đây là một tính năng tương tác của Fish. Ví dụ đơn giản thế này, bạn nhập vào command `docker`, sau đó bấm phím Lên hoăc Xuống, Fish sẽ giúp bạn tìm được lịch sử những command bạn đã từng nhập với command `docker`. Như này:

![inline-search](https://raw.githubusercontent.com/bodetaima/bodetaima.github.io/master/static/img/_posts/inline-search.png)

Fish cũng sẽ tự động xóa các câu lệnh trùng lặp, và cũng như highlight những kết quả tìm thấy.

Tính năng này chắc chắn sẽ tiết kiệm thời gian cho bạn, rất nhiều.

#### Inline auto-suggestion

Giống như [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions), Fish cũng sẵn có một tính năng như vậy. "Out-of-the-box". Cách sử dụng và tính năng có thể sẽ quen thuộc với bạn khi chuyển từ Zsh sang. Rất thông minh.

![inline-search](https://raw.githubusercontent.com/bodetaima/bodetaima.github.io/master/static/img/_posts/auto-sugestions.png)

#### Tab completion sử dụng dữ liệu từ man page

Thôi không cần trình bày về tính năng này nữa, nó quá tuyệt vời rồi. Tiết kiệm thời gian tra cứu documents cho bạn.

![inline-search](https://raw.githubusercontent.com/bodetaima/bodetaima.github.io/master/static/img/_posts/tab-completion.png)

### Hai chữ "tuy nhiên"

Tuy nhiên, Fish lại có những yếu điểm như:

- Không support history expansion (`!!`): Thi thoảng bạn quên không add sudo vào một command priviledge, `sudo !!` là rất tiện lợi. Tuy nhiên bạn có thể khắc phục với một plugin nhỏ, [bang-bang](https://github.com/oh-my-fish/plugin-bang-bang).
- Chậm hơn cả Bash: Bash là một shell có tốc độ gần như chậm nhất so với những shell khác. Fish còn chậm hơn. Điều này là dễ hiểu khi Fish cố gắng mang rất nhiều tính năng vào gói phần mềm của mình. Nhưng việc nhanh chậm hơn vài milisecond, đôi khi bạn không thể nhận ra. Bù lại, Fish ecosystems lại được phát triển tập trung và đồng bộ hơn rất nhiều so với các shell khác.
- Không tương thích và hỗ trợ POSIX. Và Fish cũng không cố gắng để hoàn thiện điều này. Có nghĩa rằng, shell script chạy được ở trên sh, Bash, Zsh không thể chạy trên Fish. Nhưng đó cũng là một trải nghiệm mới, hoặc nếu bạn không muốn, bạn vẫn có thể thêm dòng `#!/usr/bin/env bash` vào đầu file Bash.

### Kết luận

Fish là một cái tên mới, mang nhiều tính năng phong phú, hiệu quả và sẽ là một bệ phóng giúp cho năng suất làm việc của bạn leo lên một level mới. Hơn nữa, nó cũng được [document rất tốt](https://fishshell.com/docs/current/index.html) và rất dễ để [cài đặt](https://fishshell.com/).

Và đó cũng là hành trình đến với Fish của tôi.
