# 131.-Palindrome-Partitioning-leet-code-


vector<vector<string>> ans;

    bool ispalindrome(string &str, int i, int j)
    {
        while(i<j)
        {
            if(str[i]==str[j])
            {
                i++;
                j--;
            }
            else
            {
                return false;
            }
        }
        
        return true;
    }

    void solve(string &str, int i, int j, vector<string>an)
    {
        
        if(i>j)
        {
            ans.push_back(an);
            return ;
        }


        for(int k=i; k<=j; k++)
        {
            if(ispalindrome(str,i,k))
            {
                string a="";
                for(int x=i; x<=k; x++)
                {
                    a+=str[x];
                }
                an.push_back(a);
                solve(str, k+1, j,an);
                an.pop_back();
            }
        }
    }

    vector<vector<string>> partition(string s) {

        vector<string>an;

        solve(s,0,s.size()-1,an);

        return ans;
        
    }
