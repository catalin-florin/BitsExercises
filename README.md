# Prob

int main ()
{
	int a=64,i=0,b,c,z=0,n=0;
	n=sizeof(a)*8;

	for(i=0;i<n-1;i++)
	{

		if( ( (a>>i)&1) == 1 )
				{
					b=1;
				}
				else
				{
					b=0;
				}

		if( ( (a>>(i+2))&1 ) == 1 )
					{
						c=1;
					}
					else
					{
						c=0;
					}
		if(b>c)
		{
			a|=1<<(i+2);
			a&=~(1<<i);
			z++;
		}
		else if(c>b)
		{
			a|=(1<<i);
			a&=~(1<<(i+2));
			z++;
		}
		else if(c==b)
		{
			z++;
		}

if(z%2==0)
{
	i=i+2;
}

}

cout<<endl<<a;

return 0;


}
