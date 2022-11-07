# leetcode637-averageLevel


恭喜小笨蛋掌握啦～
技术来自于102，分层

        class Solution:
            def averageOfLevels(self, root: Optional[TreeNode]) -> List[float]:

                res = []
                queue = deque([root])

                if not root:
                    return []

                while queue:
                    level = []
                    for i in range(len(queue)):
                        cur = queue.popleft()
                        level.append(cur.val)
                        mid = sum(level)/ len(level)
                        if cur.left:
                            queue.append(cur.left)
                        if cur.right:
                            queue.append(cur.right)

                    res.append(mid)
                return res
